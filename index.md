# Oscillations in the hardpoint forces of M1M3



## Abstract

This technote describes oscillations seen in the M1M3 cell hardpoint
forces, these events are particularly important to understand in order to certify that the glass was safely installed on the M1M3 mirror cell, it's important to verify any vibrations that could potentially damage the mirror.
In this technote we discuss a few types of oscillations:
1. Oscillations During Slews
    - identification of events: [SITCOMTN_81_identify_oscillations_during_slew](https://github.com/lsst-sitcom/notebooks_vandv/blob/6309fee1fd026f1dbbafd5f64ffa503aa45560e4/notebooks/tel_and_site/subsys_req_ver/m1m3/SITCOMTN_81_identify_oscillations_during_slew.ipynb)
    - events caused by azimuth topple blocks: [SITCOM-1390_topple_block_vibration](https://github.com/lsst-sitcom/notebooks_vandv/blob/tickets/SITCOM-1390/notebooks/tel_and_site/subsys_req_ver/m1m3/SITCOM-1390_topple_block_vibration.ipynb)
    - events with unknown cause: [SITCOMTN_81_characterize_oscillations_during_slew](https://github.com/lsst-sitcom/notebooks_vandv/blob/6309fee1fd026f1dbbafd5f64ffa503aa45560e4/notebooks/tel_and_site/subsys_req_ver/m1m3/SITCOMTN_81_characterize_oscillations_during_slew.ipynb)
2. Strong Continuous oscillations: [SITCOMTN-081_strong_vibration_analysis](https://github.com/lsst-sitcom/notebooks_vandv/blob/develop/notebooks/tel_and_site/subsys_req_ver/m1m3/SITCOMTN-081_strong_vibration_analysis.ipynb)
3. Oscillations due to an earthquake (link to notebook, no m1m3 data)

The data analyzed in this technote is mainly made up of events during the dynamic testing of M1M3 in the second half of 2023. 
The relevant requriements are
- [LVV-11306](https://jira.lsstcorp.org/browse/LVV-11306): All vibration sources from the mirror support system combined SHALL not produce more than +/- 0.38 micron of mirror piston motion, +/0.23 micron of mirror decenter and +/ 1 e-6 degree of mirror tilt (RMS values) (see document-7271).
- For repeating oscillations we want the amplitude of oscillations be less than 400 N. This is the requirement for the mirror safety for 100,000 cycles. See disscussion under Glass Safty Criteria Number 4 (GSCN4) in [this confluence page](https://confluence.lsstcorp.org/pages/viewpage.action?pageId=222730451#SystemIntegrationTesting/VerificationBeforeGlassinstallation-RequirementsandCriteriaforM1M3GlassSafety).

A summary of the analysis in this technote can be found in the below table. 


| Type of Hardpoint Oscillation | Amplitude [N] | Repeating | Cause         | Requirements  [N]   |
|-------------------------------|---------------|-----------|---------------|------------------|
| Azimuth Slews                     | ~500          | Yes       | topple blocks         | < 400    |
| Elevation Slews                   | ###           | Yes       | Unknown                | < 400    |
| Strong continuous oscillation     | ###           | No        | control software      | < 3000    |
| Earthquake                        | No M1M3 Data  | Yes       | Mag ~6 earthquake    |  < 3000   |

<!-- the identification and characterization of these oscillations.
All of these oscillations were originally identified in the hard point measuredForces, but are seen throughout the M1M3 (and TMA) monitoring systems.
These oscillations can be broadly broken into two categories based on whether they occur during a slew.
Additionally, we mention the low amplitude continuous oscillations that occur at low elevation.
This is linked to SITCOM-918 -->

## Introduction

To ensure glass safety and the safety of all the components of the Vera C. Rubin Observatory it is imperative that the system is stable and does not expierence any large oscillations or activate any resonance modes during operations. 
In order to verify the safety of the as build system, we must investigate any identified oscillations. 
In this document we present a few of these investigations that include regularly seen oscillations during slews in both azimuth and elevation as well one time events due to problems in the control software or environmental effects such as earthquakes.
The structure of this technote is as follows, first we discuss regularly seen oscillation events during a slew. 
This includes the identification and characterization of these events as well as possible causes. 
Then, we present a select set of other one time oscillation events that occured outside of normal operations.


<!-- - Identification of slew events
- characterization of oscillation events

> - hardpoints
> - IMS
> - force actuators
> - TMA

- Fourier transform of everything
- continuous oscillations at low elevation

For the M1M3 oscillations during a slew w -->

## Oscillations During Slews

### Identification of events

Re-occuring oscillations in the M1M3 mirror cell + mirror system were identified, initially, through visual inspection of the measured forces on the hardpoint actuators during a slew. 
These hardpont force telemetries can be accessed in the EFD under the table `lsst.sal.MTM1M3.hardpointActuatorData` with the columns starting with `measuredForce`.
After the inital identification of a subset of these events we developed a heuristic method to more systematically search for them.
We compute a rolling standard deviation of the measured force on each of the six hardpoints using a 2 second window.
Then, we flag all times where the rolling standard deviation was above 100 N.
Next, for each hardpoint individually peaks within 2 seconds were accociated into a single detection in order to only flag once on each potential oscillation event.
Finally, we used a 4-second window to combine detections across hardpoints only keeping events that are detected in more than 4 of the hardpoints.
This method, is fairly complete in flagging oscillitory events, but reqires a fair amount of visual inspection to remove false positives.

An example of how oscillation events are identified is shown in figure 1.

:::{figure} ./_static/20230627_mtmount.elevation.actualTorque.png
:name: fig-oscillation-062-torque
:target: ../_images/20230627_mtmount.elevation.actualTorque.png

Chronograf screenshot of elevation torque during oscillation event.
:::

:::{figure} ./_static/Identify_events.png
:name: fig-identify-events
:target: ../_images/Identify_events.png

This figure shows the elevation of the TMA (Telescope Mount Assembly) as an orange line, the colored points show a rolling standard deviation of the hardpoint measured forces (0-5).
Oscillations are initially flagged as times during a slew with large peaks in the rolling standard deviation of at least 4 of the hardpoint forces. 
The red diamonds in this plot note two of these flagged events. 
:::

The next two subsections describe the classes of events that we discovered using this identification process. 

### Events during azimuth slews: vibrations due to the topple blocks

There are two topple blocks at az -70 and az -50 to detect the direction of the rotation in azimuth and act as a limit switch preventing the TMA from slewing in one direction over the maximum angle of its rotation. 
As the TMA slews in azimuth it hits the topple block and flips it, this contact generates vibrations in the full system that we have analyzed. 

We were able to identify and associate this class of events due to a number of azimuth only slews on on November 29 2023. 
Below we show a histogram of the aizmuth angle of the telescope when vibrations were detected. 


:::{figure} ./_static/20231129_toppleblock_position.png
:name: histogram_angle_topple_block
:target: ./_static/20231129_toppleblock_position.png
:::
Clearly these vibrations only occur around two aizmuth locations centered on -70 and -50. 
These positions roughly match the actual locations of the topple blocks. 
The spread in angle is due to the direction the TMA is rotating and the postion of the topple blocks when the collision occurs.
Therefore there is a range of a few degrees from the center of the topple block where the events can occur. 

The following plots show one such vibration event while TMA was moving in azimuth from -25 to -125 degrees.

:::{figure} ./_static/20231129_MTM1M3_vibration.png
:name: vibration_during_az_slew_toppleblock
:target: ./_static/20231129_MTM1M3_vibration.png
:::

:::{figure} ./_static/20231129_MTM1M3_zoomin.png
:name: zoom_in_vibration
:target: ./_static/20231129_MTM1M3_zoomin.png
:::

This vibration itself "during" the slew doesn't affect the settling time or other specifications, but the forces seen on the hard point are felt by the glass and could have detrimental effects.

Here we show a plot of the total hard point forces Fx, Fy, Fz and TMA acceleration during an event. 
:::{figure} ./_static/20231129_MTM1M3_hpforces.png
:name: hard_point_forces_during_topple_block
:target: ./_static/20231129_MTM1M3_hpforces.png
:::

The plot below shows and example of the measured forces on each of the 6 hardpoints from November 29 2023, where the amplitude of the vibrations seems to be more than 500 N.

:::{figure} ./_static/20231129_hp_measured_forces.png
:name: hard_point_measured_forces
:target: ./_static/20231129_hp_measured_forces.png
:::

Next, we show the same plot for an event on January 01 2024 where according to the comment on Slack that it was improved ([Slack message link](https://rubin-obs.slack.com/archives/C07Q45NBH3R/p1704371624126769))

:::{figure} ./_static/20240104_hp_measured_forces.png
:name: hard_point_measured_forces_Jan
:target: ./_static/20240104_hp_measured_forces.png
:::

On April 04 2024, we repaired the TMA topple block shock absorber ([SUMMIT-8775](https://rubinobs.atlassian.net/browse/SUMMIT-8775)), but there is no M1M3 data on TMA after that.

On November 11 2024, we tested the TMA with 5 % speed, and the HP forces when passing the topple block, are below 50 N. It doesn't show the mirror safety yet, but we can say the vibration during the tracking won't affect the image quality. 

:::{figure} ./_static/20241111_speed5_hp_measured_forces.png
:name: hard_point_measured_forces_Nov_2024_5percent
:target: ./_static/20241111_speed5_hp_measured_forces.png
:::


<!-- ### Oscillations during elevation slews 

- types of these events we see (upward and downward shift)
- we see in the ims data as well 
- amplitude of these slews are small 
- still do not know the cause of these events  -->

### Events during elevation slews: unknown cause

During the period from April 2023 to June 2023, several tests were performed consisting of elevation only slews that showcased small oscillations. 
Currently, (September 2024) the origin of these are unknown but they do not seem to compromise the hardpoint limits. 
Some examples are shown in the following plots. 
In all cases, it is required that the `MTM1M3.logevent_detailedState` is `ACTIVE` or `ACTIVEENGINEERING`, corresponding to hardpoints being active (mirrors 'raised').

:::{figure} ./_static/hp4_20230518.png
:name: hardpoints_elevation_only_slew_example1
:target: ./_static/hp4_20230518.png
:::

:::{figure} ./_static/hp9_20230529.png
:name: hardpoints_elevation_only_slew_example2
:target: ./_static/hp9_20230529.png
:::

:::{figure} ./_static/hp15_20230615.png
:name: hardpoints_elevation_only_slew_example3
:target: ./_static/hp15_20230615.png
:::

A typical distribution of maximum force on any individual hardpoint for the slews in this period looks like this:

:::{figure} ./_static/histo_hp20230623.png
:name: typical_hardpoint_distribution
:target: ./_static/histo_hp20230623.png
:::


## Strong continuous oscillation

### Summary of event 

On June 27th, during M1M3+TMA integration tests, observers noticed a powerful vibration on the TMA and M1M3.
The observers described noises similar to hammers hitting metal plates.
This was the only time such an event happened.
A summary of the event is as follows: 
1. the gateway tests were completed at 5% speed (Block 34).
2. during a slew the strong vibrations started at 2023-06-28 01:08 UTC and lasted 12 minutes until 01:20 UTC.
These vibrations were driven by the TMA elevation drives, not another subsytem.
3. In response, the force balance system was disabled and the mirror was lowered.

More details can be found in the test log ([2023, 06, 27 - M1M3 Test Log]), and jira ticket [SITCOM-1089].
It is thought that this event occurred because the TMA was slewed/homed with the force balance system on, subsequently the control software was changed to not allow this state in the future.
But, this event gives us the opportunity to understand how large vibrations will affect the M1M3 cell.
**In particular, we wanted to understand if the TMA driven oscillations could resonate with the M1M3 force balance system and cause a positive feedback loop, leading to an increase in the measured forces on the mirror.**

:::{figure} ./_static/20230627_mtmount.elevation.actualTorque.png
:name: fig-oscillation-0627-torque
:target: ./_static/20230627_mtmount.elevation.actualTorque.png

Chronograf screenshot of elevation torque during oscillation event.
:::

:::{figure} ./_static/20230627_mtmount.elevation.actualTorqueZoom.png
:name: fig-oscillation-0627-torque-zoom
:target: ./_static/20230627_mtmount.elevation.actualTorqueZoom.png

Zoom in of oscillations showing periodic behavior.
:::

The above images show the TMA torque behavior during this event.
The 12-minute duration can be seen with a peak to peak amplitude of ~500k Nm (+/- 250k).

:::{figure} ./_static/20230627_MTM1M3.hardpointActuatorData.measuredForceN.png
:name: fig-oscillation-0627-hardpoint-force
:target: ./_static/20230627_MTM1M3.hardpointActuatorData.measuredForceN.png

Chronograf screenshot of hardpoint forces during event.
:::

The above image shows the hardpoint forces, it can be noted that the event starts at 01:08.
To begin with the mirror was raised with the force balance system was active, then at 01:11:15 the force balance system was deactivated, starting at 01:11:45 the mirror was lowered and it reached the static supports at ~01:15:15.
If the M1M3 cell had any positive feedback during the event, we would expect the amplitude of the hardpoint measured forces to change with time. Or we would expect the observed frequencies of the oscillation to change with the state of the M1M3.
Based on the measured force image above the amplitude is roughly constant for each state of the mirror, and the mirror did not break away. There is no correlation between the TMA oscillation and the hardpoints behavior in the same period.

Below we show a Power Spectral Density (PSD) of the event computing it for the total event, and each of the different states of the M1M3 during the event.
We see no evolution of the vibrations during the state changes of the M1M3 cell.
**From this we conclude the cell was driven by the TMA but did not contain any positive feedback or coupling with the TMA, for this event**.

:::{figure} ./_static/20230627_hardpoints_psd.png
:name: fig-oscillation-0627-hardpoint-psd
:target: ../_images/20230627_hardpoints_psd.png

PSD of hardpoint forces for 3 of the hardpoints showing no evolution with M1M3 state (different colored lines). The black vertical lines show the vibration peaks identified in the TMA torque. It can be seen that there are a few vibration peaks in the hardpoints not seen in the TMA torque.
:::


## Earthquake Response 

We study whether the mag~6 earthquake events are safe for the mirror. There are two dates with large earthquakes:

- 2023-09-06 23:48:15 UTC
- 2023-10-31 12:33:43 UTC

### Analysis for the evening's event:  2023-09-06
#### Acceleration
1.1. Total acceleration telemetry for each of the 3 m1m3 vms channels:
![earthquake_total_acceleration](./_static/earthquake_total_acceleration.png)
It is easy to visually determine the moment when the earthquake begins and the movements are recorded.

1.2. Plot of total acceleration telemetry (with an offset) of each axis (xyz) of each channel of the m1m3 vms channels:

We analyze each of the channels separately and in the three axes. In case we could see if one of the axes is more affected than the others.
![earthquake_total_acc_channel](./_static/earthquake_total_acc_channel.png)

1.3. Plot of total acceleration telemetry (with an offset) of each axis (xyz) of the m1m3 vms channels:

Now we combine the different axes (x,y,z), where we can see that the x axis is the most affected by the earthquake movements.
![earthqueake_total_acc_axis](./_static/earthqueake_total_acc_axis.png)
The limit required to keep the mirror safe during a mag 6 earthquake must be less than 3000 N. To study this we have to analyze the HP forces along the same axes and compare it with the accelerations.

Unfortunately, we cannot do this analysis because the telescope was stationary and there is no TMA information for 2023.09-06.

#### PSD (Power Spectral Density)
We are going to analyze the Power Spectral Density

2.1. A Power Spectral Density (psd) of each axis (xyz) of each channel of the m1m3 vms data
![earthquake_psd_channels](./_static/earthquake_psd_channels.png)

We change the x-axis to better visualise the data.
![earthquake_psd_channels_zoom](./_static/earthquake_psd_channels_zoom.png)

### Analysis for the evening's event:  2023-10-31
Unfortunately, for the second night to be analyzed, 2023-10-31, where there was an earthquake event with mag~6, no information is available. Therefore, it is not possible to make any kind of analysis.

[2023, 06, 27 - m1m3 test log]: https://confluence.lsstcorp.org/display/LSSTCOM/23.06.27+-+M1M3+Test+Log
[lvv-11306]: https://jira.lsstcorp.org/browse/LVV-11306
[sitcom-1089]: https://jira.lsstcorp.org/browse/SITCOM-1089
