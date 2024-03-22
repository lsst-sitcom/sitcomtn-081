# Hardpoint oscillations



## Abstract

This tech note contains describes oscillations seen in the M1M3 cell hardpoint
forces, these events are particularly important to understand in order to verify that it is safe to put glass on the M1M3 mirror cell.
In this technote we discuss a few types of oscillations:
1. Oscillations During Slews
> - identification of events (link to notebook)
> - events caused by azimuth topple blocks (link to notebook)
> - events with unknown cause (link to notebook)
2. Strong Continuous oscillations (link to notebook)
3. Oscillations due to an earthquake (link to notebook)


<!-- the identification and characterization of these oscillations.
All of these oscillations were originally identified in the hard point measuredForces, but are seen throughout the M1M3 (and TMA) monitoring systems.
These oscillations can be broadly broken into two categories based on whether they occur during a slew.
Additionally, we mention the low amplitude continuous oscillations that occur at low elevation.
This is linked to SITCOM-918 -->

## Introduction

The structure of this technote is as follows, first we discuss oscillation events during a slew. This includes the identification and characterization of these events as well as possible causes. Then, we present a select set of other oscillations that occured outside of slewing conditions.


\=======
Just to show an example of how I am identifying oscillation events.
\=======

- Identification of slew events
- characterization of oscillation events

> - hardpoints
> - IMS
> - force actuators
> - TMA

- Fourier transform of everything
- continuous oscillations at low elevation

For the M1M3 oscillations during a slew w

## Oscillations During Slews

### Identification of events

These oscillation events were originally discovered by visual inspection of the
measured forces on the hardpoint actuators during a slew. This data can be accessed in the EFD under the table `lsst.sal.MTM1M3.hardpointActuatorData` with the columns starting with `measuredForce`.
To identify the oscillation events during a slew we used a rolling standard deviation of the measured force on each of the six hardpoints.
A 2 second window was used for the rolling and all peaks with a standard deviation above 100 N were flagged.
Next, for each hardpoint individually peaks within 2 seconds were combined in order to only flag once on each potential oscillation event.
Then, we used a 4-second window to combine peaks across hardpoints only keeping events that are detected in more than 4 of the hardpoints.

An example of how oscillation events are identified is shown in figure 1.
\>>>>>>> 8e93f80 (Added strong continuous oscillation sitcom-1089)
In this plot I show the elevation of the TMA as an orange line the points show a rolling standard deviation of the hardpoint measured forces. The red diamonds are identified events. They have a large peak in the rolling standard deviation in at least 4 hardpoints during a slew.

:::{Figure} ./_static/Identify_events.png
:::

Here is the distribution in elevation vs time of the identified events the color shows the direction of the slew.

```{image} ./_static/elevation_vs_time.png
```

### Oscillations during azimuth slews

### IMS yPosition investigation of events

I decided to start looking at the IMS data for these slew events. I noticed that there were jumps in the ims `yPosition`  that corresponded with these events.
The `yPosition` jumps seemed to fall into 4 categories that I poorly named:
\- upward shift
\- downward shift
\- p cygni
\- scoop

I also noticed that sometimes regular oscillations (wiggles) were superimposed on the `yPosition`  shifts, and I separated those out
For the following few plots I am showing one of the above groups, the top panel is upward slews, and the bottom panel is downward slews. The x axis is time relative to event, and the y axis is the ims yPosition

### Upward shifts

```{image} ./_static/ims_yposition_upward_shift_no_wiggles.png
```

```{image} ./_static/ims_yposition_upward_shift_small_wiggles.png
```

### downward shifts

```{image} ./_static/ims_yposition_downward_shift_no_wiggles.png
```

```{image} ./_static/ims_yposition_downward_shift_small_wiggles.png
```

### p cygni

```{image} ./_static/ims_yposition_p_cygni_no_wiggles.png
```

```{image} ./_static/ims_yposition_p_cygni_small_wiggles.png
```

### scoop

```{image} ./_static/ims_yposition_scoop_no_wiggles.png
```

The p cygni/scoop events seem to be a different type of oscillation, so I will include the rest of their plots at the end.

### Measured forces

Next I looked back at the `lsst.sal.MTM1M3.hardpointActuatorData`  hardpoint `measuredForces`, again breaking them up by group. Here I show examples of the delta force from the mean before the event (with an offset) as a function of time.

```{image} ./_static/DeltaForce_upward_shift.png
```

```{image} ./_static/DeltaForce_downward_shift.png
```

These two exampes illustrate the behaviour of all of these events (all were visually inpected) where ghe measured force amplitude was always much lower for hardpoints 1 & 4, corresponding to the hardpoints in line with the elevation rotation axis

### Full summary plots

Here are some examples of events showing the ims (position/rotation) as a function of time and the harpoiont measured force as a reference. It looks like there may be something interesting in the rotations as well

```{image} ./_static/summary_upward_shift.png
```

```{image} ./_static/summary_downward_shift.png
```

### Elevation of upward/downward shift events

inally, here is the elevation vs time plot where I color coded based on event category (shape shows upward/downward slew). This shows some consistent behaviour in the elevation of these oscillation events.

## Next Steps

From Petr the next few steps are:

- Get PSD out of oscillation (of measuredForces), find dominant frequency (shall be one, around 7Hz), see that’s good fit for duration of the oscillation, get out initial peak (energy) + dumping, fit it to curve to find “frequency shift”
- Also look at <https://ts-xml.lsst.io/sal_interfaces/MTM1M3.html#forceactuatordata> - primaryCylinderFollowingError and secondaryCylinderFollowingError
- Chronograf dashboards can be accessed via URL. Providing a HTML page with events, their dates, and links to various Chronograf displays might be interesting as well
- example url: <https://summit-lsp.lsst.codes/chronograf/sources/1/dashboards/207>?refresh=Paused&tempVa\[…\]10%3A07%3A57.353Z&zoomedUpper=2023-05-30T10%3A08%3A02.962Z
- <https://en.wikipedia.org/wiki/Damping> - you need to find phase angle of couple of hundreds oscillators
- And if you can mention the FRACAS - <https://jira.lsstcorp.org/browse/FRACAS-158> - on Confluence
- More on force actuators following error. Those are errors in actuator space. Shall be converted to the mirror space. Best I can do would be providing function in ts_cRIOpy which can do that - you feed in force actuators values, out goes 3 * 156 of XYZ forces

```{image} ./_static/labeled_elevation_vs_time.png
```

## Other Oscillations

In this section we describe other oscillations seen in the M1M3 system.

### Strong continuous oscillation

On June 27th, during M1M3+TMA integration tests, observers noticed a powerful vibration on the TMA and M1M3.
The observers described noises similar to hammers hitting metal plates.
This was the only time such an event happened.
A summary of the event is as follows: the gateway tests were completed at 5% speed (Block 34).
Then, during a slew the strong vibrations started at 2023-06-28 01:08 UTC and lasted 12 minutes until 01:20 UTC.
The vibrations were driven by the TMA elevation drives, not another subsytem.
In response, the force balance system was disabled and the mirror was lowered.
More details can be found in the test log ([2023, 06, 27 - M1M3 Test Log]), and jira ticket [SITCOM-1089].
It is thought that this event occurred because the TMA was slewed/homed with the force balance system on, subsequently the control software was changed to not allow this state in the future.
But, this event gives us the opportunity to understand how large vibrations will affect the M1M3 cell.
**In particular, we wanted to understand if the TMA driven oscillations resonated with the M1M3 force balance system causing a positive feedback loop in the force on the mirror.**

:::{figure} ./_static/20230627_mtmount.elevation.actualTorque.png
:name: fig-oscillation-0627-torque
:target: ../_images/20230627_mtmount.elevation.actualTorque.png

Chronograf screenshot of elevation torque during oscillation event.
:::

:::{figure} ./_static/20230627_mtmount.elevation.actualTorqueZoom.png
:name: fig-oscillation-0627-torque-zoom
:target: ../_images/20230627_mtmount.elevation.actualTorqueZoom.png

Zoom in of oscillations showing periodic behavior.
:::

The above images show the TMA torque behavior during this event.
The 12-minute duration can be seen with a peak to peak amplitude of ~500k Nm (+/- 250k).

:::{figure} ./_static/20230627_MTM1M3.hardpointActuatorData.measuredForceN.png
:name: fig-oscillation-0627-hardpoint-force
:target: ../_images/20230627_MTM1M3.hardpointActuatorData.measuredForceN.png

Chronograf screenshot of hardpoint forces during event.
:::

The above image shows the hardpoint forces, it can be noted that the event starts at 01:08.
To begin with the mirror was raised with the force balance system was active, then at 01:11:15 the force balance system was deactivated, starting at 01:11:45 the mirror was lowered and it reached the static supports at ~01:15:15.
If the M1M3 cell had any positive feedback during the event, we would expect the amplitude of the hardpoint measured forces to change with time. Or we would expect the observed frequencies of the oscillation to change with the state of the M1M3.
Based on the measured force image above the amplitude is roughly constant for each state of the mirror, and the Mirror did not break away.
*what is requirement for continuous oscillation: LTS-88-REQ-0065 All vibration sources from the mirror support system combined SHALL not produce more than +/- 0.38 micron of mirror piston motion, +/0.23 micron of mirror decenter and +/ 1 e-6 degree of mirror tilt (RMS values)*
[LVV-11306]
Below we show a PSD of the event computing it for the total event, and each of the different states of the M1M3 during the event.
We see no evolution of the vibrations during the state changes of the M1M3 cell.
**From this we conclude the cell was driven by the TMA but did not contain any positive feedback or coupling with the TMA, for this event**.

:::{figure} ./_static/20230627_hardpoints_psd.png
:name: fig-oscillation-0627-hardpoint-psd
:target: ../_images/20230627_hardpoints_psd.png

PSD of hardpoint forces for 3 of the hardpoints showing no evolution with M1M3 state (different colored lines). The black vertical lines show the vibration peaks identified in the TMA torque. It can be seen that there are a few vibration peaks in the hardpoints not seen in the TMA torque.
:::

## Apendix: p cygni/scoop

### Measured forces

```{image} ./_static/DeltaForce_p_cygni.png
```

```{image} ./_static/DeltaForce_scoop.png
```

### Full summary plots

```{image} ./_static/summary_p_cygni.png
```

```{image} ./_static/summary_scoop.png
```

\>>>>>>> 3323e26 (First update)

[2023, 06, 27 - m1m3 test log]: https://confluence.lsstcorp.org/display/LSSTCOM/23.06.27+-+M1M3+Test+Log
[lvv-11306]: https://jira.lsstcorp.org/browse/LVV-11306
[sitcom-1089]: https://jira.lsstcorp.org/browse/SITCOM-1089
