Last login: Mon Jul 29 14:42:14 on ttys005
hyeyunpark@Hye-Yuns-MacBook-Pro ~ % defaults write org.xquartz.X11 enable_render_extension 0
hyeyunpark@Hye-Yuns-MacBook-Pro ~ % pwd
/Users/hyeyunpark
hyeyunpark@Hye-Yuns-MacBook-Pro ~ % ls 
Desktop		Downloads	Movies		Pictures
Documents	Library		Music		Public
hyeyunpark@Hye-Yuns-MacBook-Pro ~ % cd Desktop 
hyeyunpark@Hye-Yuns-MacBook-Pro Desktop % ls
hyeyunpark@Hye-Yuns-MacBook-Pro Desktop % cd -
~
hyeyunpark@Hye-Yuns-MacBook-Pro ~ % ls
Desktop		Downloads	Movies		Pictures
Documents	Library		Music		Public
hyeyunpark@Hye-Yuns-MacBook-Pro ~ % cd Documents/gi 
cd: no such file or directory: Documents/gi
hyeyunpark@Hye-Yuns-MacBook-Pro ~ % cd Documents/git
hyeyunpark@Hye-Yuns-MacBook-Pro git % ls
notebooks_vandv	ts_config_ocs
hyeyunpark@Hye-Yuns-MacBook-Pro git % cd notebooks_vandv 
hyeyunpark@Hye-Yuns-MacBook-Pro notebooks_vandv % ls
COPYRIGHT	README.md	python		ups
LICENSE		notebooks	tests
hyeyunpark@Hye-Yuns-MacBook-Pro notebooks_vandv % cd notebooks 
hyeyunpark@Hye-Yuns-MacBook-Pro notebooks % ls
Anemom_Accel_Test_Analysis_sample_notebook.ipynb
Error_Trend_Plot_sample_notebook.ipynb
MTMount_Characterization_sample_notebook.ipynb
MT_Accelerometers_Angular_Acceleration_sample_notebook.ipynb
Query_EFD_sample_notebook.ipynb
SAL Script - Slew and Track by Duration.ipynb
SAL Script - Slew and Track one Target.ipynb
Soak Test Prototype.ipynb
Tpoint_Input_File_Check_sample_notebook.ipynb
proj_sys_eng
tel_and_site
hyeyunpark@Hye-Yuns-MacBook-Pro notebooks % git branch
  develop
* tickets/SITCOM-1116
hyeyunpark@Hye-Yuns-MacBook-Pro notebooks % git fetch
remote: Enumerating objects: 2197, done.
remote: Counting objects: 100% (1070/1070), done.
remote: Compressing objects: 100% (370/370), done.
remote: Total 2197 (delta 680), reused 925 (delta 618), pack-reused 1127 (from 1)
Receiving objects: 100% (2197/2197), 86.86 MiB | 10.70 MiB/s, done.
Resolving deltas: 100% (1148/1148), completed with 22 local objects.
From https://github.com/lsst-sitcom/notebooks_vandv
 * [new branch]      SUMMIT-7944         -> origin/SUMMIT-7944
   a2880b7..5b9c18b  develop             -> origin/develop
 * [new branch]      ltoribiosc-patch-1  -> origin/ltoribiosc-patch-1
 * [new branch]      revert-115-tickets/SITCOM-1243 -> origin/revert-115-tickets/SITCOM-1243
 * [new branch]      sitcom_1202         -> origin/sitcom_1202
 + 975f468...a724452 tickets/SITCOM-1002 -> origin/tickets/SITCOM-1002  (forced update)
 * [new branch]      tickets/SITCOM-1120 -> origin/tickets/SITCOM-1120
   13b857b..b7e0368  tickets/SITCOM-1131 -> origin/tickets/SITCOM-1131
 * [new branch]      tickets/SITCOM-1146 -> origin/tickets/SITCOM-1146
 * [new branch]      tickets/SITCOM-1160 -> origin/tickets/SITCOM-1160
 * [new branch]      tickets/SITCOM-1171 -> origin/tickets/SITCOM-1171
 * [new branch]      tickets/SITCOM-1179 -> origin/tickets/SITCOM-1179
 * [new branch]      tickets/SITCOM-1180 -> origin/tickets/SITCOM-1180
 * [new branch]      tickets/SITCOM-1223 -> origin/tickets/SITCOM-1223
 * [new branch]      tickets/SITCOM-1224 -> origin/tickets/SITCOM-1224
 * [new branch]      tickets/SITCOM-1231 -> origin/tickets/SITCOM-1231
 * [new branch]      tickets/SITCOM-1233 -> origin/tickets/SITCOM-1233
 * [new branch]      tickets/SITCOM-1282 -> origin/tickets/SITCOM-1282
 * [new branch]      tickets/SITCOM-1306 -> origin/tickets/SITCOM-1306
 * [new branch]      tickets/SITCOM-1316 -> origin/tickets/SITCOM-1316
 * [new branch]      tickets/SITCOM-1317 -> origin/tickets/SITCOM-1317
 * [new branch]      tickets/SITCOM-1345 -> origin/tickets/SITCOM-1345
 * [new branch]      tickets/SITCOM-1348 -> origin/tickets/SITCOM-1348
 * [new branch]      tickets/SITCOM-1397 -> origin/tickets/SITCOM-1397
 * [new branch]      tickets/SITCOM-1399 -> origin/tickets/SITCOM-1399
 * [new branch]      tickets/SITCOM-1400 -> origin/tickets/SITCOM-1400
 * [new branch]      tickets/SITCOM-1467 -> origin/tickets/SITCOM-1467
 * [new branch]      tickets/SITCOM-1488 -> origin/tickets/SITCOM-1488
 * [new branch]      tickets/SITCOM-1508 -> origin/tickets/SITCOM-1508
 * [new branch]      tickets/SITCOM-756  -> origin/tickets/SITCOM-756
 * [new branch]      tickets/SITCOM-772  -> origin/tickets/SITCOM-772
 + 6309fee...a39d400 tickets/SITCOM-918  -> origin/tickets/SITCOM-918  (forced update)
   1e6d920..3acc88f  tickets/SUMMIT-7944 -> origin/tickets/SUMMIT-7944
 * [new branch]      tickets/sitcom-1412 -> origin/tickets/sitcom-1412
hyeyunpark@Hye-Yuns-MacBook-Pro notebooks % git checkout -b tickets/SITCOM-1390 origin/tickets/SITCOM-1390
fatal: 'origin/tickets/SITCOM-1390' is not a commit and a branch 'tickets/SITCOM-1390' cannot be created from it
hyeyunpark@Hye-Yuns-MacBook-Pro notebooks % git switch tickets/SITCOM-1390
fatal: invalid reference: tickets/SITCOM-1390
hyeyunpark@Hye-Yuns-MacBook-Pro notebooks % git branch -al                
  develop
* tickets/SITCOM-1116
  remotes/origin/HEAD -> origin/develop
  remotes/origin/SITCOM-538
  remotes/origin/SUMMIT-7944
  remotes/origin/SUMMIT-8129
  remotes/origin/develop
  remotes/origin/gabrirod86-patch-1
  remotes/origin/ltoribiosc-patch-1
  remotes/origin/revert-115-tickets/SITCOM-1243
  remotes/origin/sitcom_1202
  remotes/origin/testcase/LVV-T1783
  remotes/origin/testcase/LVV-T1784
  remotes/origin/testcase/LVV-T1788
  remotes/origin/testcase/LVV-T1789
  remotes/origin/testcase/LVV-T1791
  remotes/origin/testcase/LVV-T1792
  remotes/origin/testcase/LVV-T2668
  remotes/origin/testcase/LVV-T2739
  remotes/origin/testcase/LVV-T2873
  remotes/origin/testcase/LVV-T2969
  remotes/origin/tickets/DM-35839
  remotes/origin/tickets/SITCOM-1002
  remotes/origin/tickets/SITCOM-1006
  remotes/origin/tickets/SITCOM-1023
  remotes/origin/tickets/SITCOM-1048
  remotes/origin/tickets/SITCOM-1095
  remotes/origin/tickets/SITCOM-1102
  remotes/origin/tickets/SITCOM-1115
  remotes/origin/tickets/SITCOM-1116
  remotes/origin/tickets/SITCOM-1120
  remotes/origin/tickets/SITCOM-1131
  remotes/origin/tickets/SITCOM-1136
  remotes/origin/tickets/SITCOM-1146
  remotes/origin/tickets/SITCOM-1160
  remotes/origin/tickets/SITCOM-1171
  remotes/origin/tickets/SITCOM-1179
  remotes/origin/tickets/SITCOM-1180
  remotes/origin/tickets/SITCOM-1223
  remotes/origin/tickets/SITCOM-1224
  remotes/origin/tickets/SITCOM-1231
  remotes/origin/tickets/SITCOM-1233
  remotes/origin/tickets/SITCOM-1282
  remotes/origin/tickets/SITCOM-1306
  remotes/origin/tickets/SITCOM-1316
  remotes/origin/tickets/SITCOM-1317
  remotes/origin/tickets/SITCOM-1345
  remotes/origin/tickets/SITCOM-1348
  remotes/origin/tickets/SITCOM-1397
  remotes/origin/tickets/SITCOM-1399
  remotes/origin/tickets/SITCOM-1400
  remotes/origin/tickets/SITCOM-1467
  remotes/origin/tickets/SITCOM-1488
  remotes/origin/tickets/SITCOM-1508
  remotes/origin/tickets/SITCOM-517
  remotes/origin/tickets/SITCOM-680
  remotes/origin/tickets/SITCOM-701
  remotes/origin/tickets/SITCOM-710
  remotes/origin/tickets/SITCOM-724
  remotes/origin/tickets/SITCOM-756
  remotes/origin/tickets/SITCOM-772
  remotes/origin/tickets/SITCOM-854
  remotes/origin/tickets/SITCOM-858
  remotes/origin/tickets/SITCOM-880
  remotes/origin/tickets/SITCOM-899
  remotes/origin/tickets/SITCOM-910
  remotes/origin/tickets/SITCOM-918
  remotes/origin/tickets/SUMMIT-5782
  remotes/origin/tickets/SUMMIT-7944
  remotes/origin/tickets/sitcom-1412
  remotes/origin/update_ffw_azel_grid
 ^X
  remotes/origin/tickets/SITCOM-1397
  remotes/origin/tickets/SITCOM-1399
  remotes/origin/tickets/SITCOM-1400
  remotes/origin/tickets/SITCOM-1467
  remotes/origin/tickets/SITCOM-1488
  remotes/origin/tickets/SITCOM-1508
  remotes/origin/tickets/SITCOM-517
  remotes/origin/tickets/SITCOM-680
  remotes/origin/tickets/SITCOM-701
  remotes/origin/tickets/SITCOM-710
  remotes/origin/tickets/SITCOM-724
  remotes/origin/tickets/SITCOM-756
  remotes/origin/tickets/SITCOM-772
  remotes/origin/tickets/SITCOM-854
  remotes/origin/tickets/SITCOM-858
  remotes/origin/tickets/SITCOM-880
  remotes/origin/tickets/SITCOM-899
  remotes/origin/tickets/SITCOM-910
  remotes/origin/tickets/SITCOM-918
  remotes/origin/tickets/SUMMIT-5782
  remotes/origin/tickets/SUMMIT-7944
  remotes/origin/tickets/sitcom-1412
  remotes/origin/update_ffw_azel_grid
 ^X
  remotes/origin/tickets/SITCOM-1397
  remotes/origin/tickets/SITCOM-1399
  remotes/origin/tickets/SITCOM-1400
  remotes/origin/tickets/SITCOM-1467
  remotes/origin/tickets/SITCOM-1488
  remotes/origin/tickets/SITCOM-1508
  remotes/origin/tickets/SITCOM-517
  remotes/origin/tickets/SITCOM-680
  remotes/origin/tickets/SITCOM-701
  remotes/origin/tickets/SITCOM-710
  remotes/origin/tickets/SITCOM-724
  remotes/origin/tickets/SITCOM-756
  remotes/origin/tickets/SITCOM-772
  remotes/origin/tickets/SITCOM-854
  remotes/origin/tickets/SITCOM-858
  remotes/origin/tickets/SITCOM-880
  remotes/origin/tickets/SITCOM-899
  remotes/origin/tickets/SITCOM-910
  remotes/origin/tickets/SITCOM-918
  remotes/origin/tickets/SUMMIT-5782
  remotes/origin/tickets/SUMMIT-7944
  remotes/origin/tickets/sitcom-1412
  remotes/origin/update_ffw_azel_grid

hyeyunpark@Hye-Yuns-MacBook-Pro notebooks % 
hyeyunpark@Hye-Yuns-MacBook-Pro notebooks % git branch tickets/SITCOM-1390
hyeyunpark@Hye-Yuns-MacBook-Pro notebooks % ls
Anemom_Accel_Test_Analysis_sample_notebook.ipynb
Error_Trend_Plot_sample_notebook.ipynb
MTMount_Characterization_sample_notebook.ipynb
MT_Accelerometers_Angular_Acceleration_sample_notebook.ipynb
Query_EFD_sample_notebook.ipynb
SAL Script - Slew and Track by Duration.ipynb
SAL Script - Slew and Track one Target.ipynb
Soak Test Prototype.ipynb
Tpoint_Input_File_Check_sample_notebook.ipynb
proj_sys_eng
tel_and_site
hyeyunpark@Hye-Yuns-MacBook-Pro notebooks % pwd
/Users/hyeyunpark/Documents/git/notebooks_vandv/notebooks
hyeyunpark@Hye-Yuns-MacBook-Pro notebooks % cd tel_and_site 
hyeyunpark@Hye-Yuns-MacBook-Pro tel_and_site % ls
subsys_req_ver
hyeyunpark@Hye-Yuns-MacBook-Pro tel_and_site % cd subsys_req_ver 
hyeyunpark@Hye-Yuns-MacBook-Pro subsys_req_ver % cd m1m3
hyeyunpark@Hye-Yuns-MacBook-Pro m1m3 % ls
LVV-T231-analysis-offline.ipynb
LVV-T232-analysis_actuators.ipynb
LVV-T235-SITCOM-810.ipynb
LVV-T235-analysis.ipynb
SITCOM-1089_strong_vibration_analysis.ipynb
SITCOM-760_Analysis.ipynb
SITCOM-761_vms_io_and_plotting.ipynb
SITCOM-771_analysis.ipynb
SITCOM-797_MTM1M3_Position_Stability_17Nov23.ipynb
SITCOM-799_Analysis.ipynb
SITCOM-818_SITCOMTN-083.ipynb
SITCOMTN-079_LUT_analysis_improvement.ipynb
SITCOMTN-079_LUT_analysis_measured_forces.ipynb
SITCOMTN-079_LUT_analysis_updates.ipynb
SITCOMTN-092_analysis_inertia_compensation.ipynb
SITCOMTN-092_m1m3_ics_historical_analysis.ipynb
SITCOMTN-095_settling_big_vibrations.ipynb
SITCOMTN-095_settling_time_chi2test.ipynb
SITCOMTN-095_settling_time_pass_fail.ipynb
SITCOMTN-095_settling_time_rms.ipynb
ims_elevation_slew_explore.ipynb
sitcom-797_ics_slewing_analysis_positioning.ipynb
hyeyunpark@Hye-Yuns-MacBook-Pro m1m3 % mv ~/Downloads/SITCOM-1390_topple_block_vibration.ipynb .
hyeyunpark@Hye-Yuns-MacBook-Pro m1m3 % ls
LVV-T231-analysis-offline.ipynb
LVV-T232-analysis_actuators.ipynb
LVV-T235-SITCOM-810.ipynb
LVV-T235-analysis.ipynb
SITCOM-1089_strong_vibration_analysis.ipynb
SITCOM-1390_topple_block_vibration.ipynb
SITCOM-760_Analysis.ipynb
SITCOM-761_vms_io_and_plotting.ipynb
SITCOM-771_analysis.ipynb
SITCOM-797_MTM1M3_Position_Stability_17Nov23.ipynb
SITCOM-799_Analysis.ipynb
SITCOM-818_SITCOMTN-083.ipynb
SITCOMTN-079_LUT_analysis_improvement.ipynb
SITCOMTN-079_LUT_analysis_measured_forces.ipynb
SITCOMTN-079_LUT_analysis_updates.ipynb
SITCOMTN-092_analysis_inertia_compensation.ipynb
SITCOMTN-092_m1m3_ics_historical_analysis.ipynb
SITCOMTN-095_settling_big_vibrations.ipynb
SITCOMTN-095_settling_time_chi2test.ipynb
SITCOMTN-095_settling_time_pass_fail.ipynb
SITCOMTN-095_settling_time_rms.ipynb
ims_elevation_slew_explore.ipynb
sitcom-797_ics_slewing_analysis_positioning.ipynb
hyeyunpark@Hye-Yuns-MacBook-Pro m1m3 % git add SITCOM-1390_topple_block_vibration.ipynb
hyeyunpark@Hye-Yuns-MacBook-Pro m1m3 % git commit -m "add vibration analysis on topple block"
[tickets/SITCOM-1116 e7bab46] add vibration analysis on topple block
 1 file changed, 1227 insertions(+)
 create mode 100644 notebooks/tel_and_site/subsys_req_ver/m1m3/SITCOM-1390_topple_block_vibration.ipynb
hyeyunpark@Hye-Yuns-MacBook-Pro m1m3 % git push
Enumerating objects: 12, done.
Counting objects: 100% (12/12), done.
Delta compression using up to 8 threads
Compressing objects: 100% (6/6), done.
Writing objects: 100% (7/7), 10.84 KiB | 10.84 MiB/s, done.
Total 7 (delta 3), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (3/3), completed with 3 local objects.
remote: 
remote: Create a pull request for 'tickets/SITCOM-1116' on GitHub by visiting:
remote:      https://github.com/lsst-sitcom/notebooks_vandv/pull/new/tickets/SITCOM-1116
remote: 
To https://github.com/lsst-sitcom/notebooks_vandv.git
 * [new branch]      tickets/SITCOM-1116 -> tickets/SITCOM-1116
hyeyunpark@Hye-Yuns-MacBook-Pro m1m3 % git branch
  develop
* tickets/SITCOM-1116
  tickets/SITCOM-1390
hyeyunpark@Hye-Yuns-MacBook-Pro m1m3 % git switch tickets/SITCOM-1390
Switched to branch 'tickets/SITCOM-1390'
hyeyunpark@Hye-Yuns-MacBook-Pro m1m3 % ls
LVV-T231-analysis-offline.ipynb
LVV-T232-analysis_actuators.ipynb
LVV-T235-SITCOM-810.ipynb
LVV-T235-analysis.ipynb
SITCOM-1089_strong_vibration_analysis.ipynb
SITCOM-760_Analysis.ipynb
SITCOM-761_vms_io_and_plotting.ipynb
SITCOM-771_analysis.ipynb
SITCOM-797_MTM1M3_Position_Stability_17Nov23.ipynb
SITCOM-799_Analysis.ipynb
SITCOM-818_SITCOMTN-083.ipynb
SITCOMTN-079_LUT_analysis_improvement.ipynb
SITCOMTN-079_LUT_analysis_measured_forces.ipynb
SITCOMTN-079_LUT_analysis_updates.ipynb
SITCOMTN-092_analysis_inertia_compensation.ipynb
SITCOMTN-092_m1m3_ics_historical_analysis.ipynb
SITCOMTN-095_settling_big_vibrations.ipynb
SITCOMTN-095_settling_time_chi2test.ipynb
SITCOMTN-095_settling_time_pass_fail.ipynb
SITCOMTN-095_settling_time_rms.ipynb
ims_elevation_slew_explore.ipynb
sitcom-797_ics_slewing_analysis_positioning.ipynb
hyeyunpark@Hye-Yuns-MacBook-Pro m1m3 % ls
LVV-T231-analysis-offline.ipynb
LVV-T232-analysis_actuators.ipynb
LVV-T235-SITCOM-810.ipynb
LVV-T235-analysis.ipynb
SITCOM-1089_strong_vibration_analysis.ipynb
SITCOM-760_Analysis.ipynb
SITCOM-761_vms_io_and_plotting.ipynb
SITCOM-771_analysis.ipynb
SITCOM-797_MTM1M3_Position_Stability_17Nov23.ipynb
SITCOM-799_Analysis.ipynb
SITCOM-818_SITCOMTN-083.ipynb
SITCOMTN-079_LUT_analysis_improvement.ipynb
SITCOMTN-079_LUT_analysis_measured_forces.ipynb
SITCOMTN-079_LUT_analysis_updates.ipynb
SITCOMTN-092_analysis_inertia_compensation.ipynb
SITCOMTN-092_m1m3_ics_historical_analysis.ipynb
SITCOMTN-095_settling_big_vibrations.ipynb
SITCOMTN-095_settling_time_chi2test.ipynb
SITCOMTN-095_settling_time_pass_fail.ipynb
SITCOMTN-095_settling_time_rms.ipynb
ims_elevation_slew_explore.ipynb
sitcom-797_ics_slewing_analysis_positioning.ipynb
hyeyunpark@Hye-Yuns-MacBook-Pro m1m3 % git branch                          
  develop
  tickets/SITCOM-1116
* tickets/SITCOM-1390
hyeyunpark@Hye-Yuns-MacBook-Pro m1m3 % git switch tickets/SITCOM-1116
Switched to branch 'tickets/SITCOM-1116'
Your branch is up to date with 'origin/tickets/SITCOM-1116'.
hyeyunpark@Hye-Yuns-MacBook-Pro m1m3 % mv SITCOM-1390_topple_block_vibration.ipynb ~/Downloads/.
hyeyunpark@Hye-Yuns-MacBook-Pro m1m3 % git switch tickets/SITCOM-1390
Switched to branch 'tickets/SITCOM-1390'
hyeyunpark@Hye-Yuns-MacBook-Pro m1m3 % mv ~/Downloads/SITCOM-1390_topple_block_vibration.ipynb .
hyeyunpark@Hye-Yuns-MacBook-Pro m1m3 % git add SITCOM-1390_topple_block_vibration.ipynb
hyeyunpark@Hye-Yuns-MacBook-Pro m1m3 % git commit "add analysis on vibration from topple block"
error: pathspec 'add analysis on vibration from topple block' did not match any file(s) known to git
hyeyunpark@Hye-Yuns-MacBook-Pro m1m3 % git commit -m "add analysis on vibration from topple block"
[tickets/SITCOM-1390 1d1159f] add analysis on vibration from topple block
 1 file changed, 1227 insertions(+)
 create mode 100644 notebooks/tel_and_site/subsys_req_ver/m1m3/SITCOM-1390_topple_block_vibration.ipynb
hyeyunpark@Hye-Yuns-MacBook-Pro m1m3 % git push
fatal: The current branch tickets/SITCOM-1390 has no upstream branch.
To push the current branch and set the remote as upstream, use

    git push --set-upstream origin tickets/SITCOM-1390

To have this happen automatically for branches without a tracking
upstream, see 'push.autoSetupRemote' in 'git help config'.

hyeyunpark@Hye-Yuns-MacBook-Pro m1m3 % git push --set-upstream origin tickets/SITCOM-1390
Enumerating objects: 12, done.
Counting objects: 100% (12/12), done.
Delta compression using up to 8 threads
Compressing objects: 100% (6/6), done.
Writing objects: 100% (7/7), 10.85 KiB | 10.85 MiB/s, done.
Total 7 (delta 3), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (3/3), completed with 3 local objects.
remote: 
remote: Create a pull request for 'tickets/SITCOM-1390' on GitHub by visiting:
remote:      https://github.com/lsst-sitcom/notebooks_vandv/pull/new/tickets/SITCOM-1390
remote: 
To https://github.com/lsst-sitcom/notebooks_vandv.git
 * [new branch]      tickets/SITCOM-1390 -> tickets/SITCOM-1390
branch 'tickets/SITCOM-1390' set up to track 'origin/tickets/SITCOM-1390'.
hyeyunpark@Hye-Yuns-MacBook-Pro m1m3 % git fetch
hyeyunpark@Hye-Yuns-MacBook-Pro m1m3 % ls
LVV-T231-analysis-offline.ipynb
LVV-T232-analysis_actuators.ipynb
LVV-T235-SITCOM-810.ipynb
LVV-T235-analysis.ipynb
SITCOM-1089_strong_vibration_analysis.ipynb
SITCOM-1390_topple_block_vibration.ipynb
SITCOM-760_Analysis.ipynb
SITCOM-761_vms_io_and_plotting.ipynb
SITCOM-771_analysis.ipynb
SITCOM-797_MTM1M3_Position_Stability_17Nov23.ipynb
SITCOM-799_Analysis.ipynb
SITCOM-818_SITCOMTN-083.ipynb
SITCOMTN-079_LUT_analysis_improvement.ipynb
SITCOMTN-079_LUT_analysis_measured_forces.ipynb
SITCOMTN-079_LUT_analysis_updates.ipynb
SITCOMTN-092_analysis_inertia_compensation.ipynb
SITCOMTN-092_m1m3_ics_historical_analysis.ipynb
SITCOMTN-095_settling_big_vibrations.ipynb
SITCOMTN-095_settling_time_chi2test.ipynb
SITCOMTN-095_settling_time_pass_fail.ipynb
SITCOMTN-095_settling_time_rms.ipynb
ims_elevation_slew_explore.ipynb
sitcom-797_ics_slewing_analysis_positioning.ipynb
hyeyunpark@Hye-Yuns-MacBook-Pro m1m3 % git switch SITCOM-918
fatal: invalid reference: SITCOM-918
hyeyunpark@Hye-Yuns-MacBook-Pro m1m3 % git switch tickets/SITCOM-918
branch 'tickets/SITCOM-918' set up to track 'origin/tickets/SITCOM-918'.
Switched to a new branch 'tickets/SITCOM-918'
hyeyunpark@Hye-Yuns-MacBook-Pro m1m3 % ls
SITCOM-1136_M1M3_analysis_stability_tracking.ipynb
SITCOM-1165_m1m3_bump_test_error_and_measured_forces.ipynb
SITCOM-760_Analysis.ipynb
SITCOM-761_vms_io_and_plotting.ipynb
SITCOMTN-079_LUT_analysis_improvement.ipynb
SITCOMTN-079_LUT_analysis_measured_forces.ipynb
SITCOMTN-079_LUT_analysis_updates.ipynb
SITCOMTN-081_strong_vibration_analysis.ipynb
SITCOMTN-082_analysis_individual_hp_breakaway.ipynb
SITCOMTN-082_axial_breakaway_during_slew.ipynb
SITCOMTN-082_hardpoint_breakaway_analysis.ipynb
SITCOMTN-082_individual_hardpoint_breakaway_test_analysis_offline.ipynb
SITCOMTN-083_actuator_bump_test_history.ipynb
SITCOMTN-083_analyzing_bump_tests_data_for_maximal_overshoot.ipynb
SITCOMTN-083_fa_error_lag_analysis.ipynb
SITCOMTN-083_m1m3_bump_test_failure_analysis.ipynb
SITCOMTN-084_create_data_analysis_script_notebook_for_LVV-T235.ipynb
SITCOMTN-084_ims_slewing_azimuth_analysis_positioning.ipynb
SITCOMTN-084_ims_slewing_elevation_analysis_positioning.ipynb
SITCOMTN-084_position_repeatability_after_parking.ipynb
SITCOMTN-084_slewing_analysis_positioning.ipynb
SITCOMTN-092_analysis_actuators_and_actuators_movie.ipynb
SITCOMTN-092_force_actuator_snapshot_during_slew.ipynb
SITCOMTN-092_inertia_compensation_single_slew_hp.ipynb
SITCOMTN-092_m1m3_ics_historical_analysis.ipynb
SITCOMTN-095_settling_time_chi2test.ipynb
SITCOMTN-095_settling_time_pass_fail.ipynb
SITCOMTN-095_settling_time_rms.ipynb
SITCOMTN_81_20231128_topple_block_slews.ipynb
SITCOMTN_81_elevation_slew_oscillations.ipynb
SITCOMTN_81_identify_oscillations_during_slew.ipynb
ims_elevation_slew_explore.ipynb
hyeyunpark@Hye-Yuns-MacBook-Pro m1m3 % cd ~/Documents/git
hyeyunpark@Hye-Yuns-MacBook-Pro git % ls
notebooks_vandv	ts_config_ocs
hyeyunpark@Hye-Yuns-MacBook-Pro git % git clone https://github.com/lsst-sitcom/sitcomtn-081.git
Cloning into 'sitcomtn-081'...
remote: Enumerating objects: 79, done.
remote: Counting objects: 100% (79/79), done.
remote: Compressing objects: 100% (61/61), done.
remote: Total 79 (delta 14), reused 74 (delta 10), pack-reused 0 (from 0)
Receiving objects: 100% (79/79), 9.12 MiB | 4.55 MiB/s, done.
Resolving deltas: 100% (14/14), done.
hyeyunpark@Hye-Yuns-MacBook-Pro git % git branch
fatal: not a git repository (or any of the parent directories): .git
hyeyunpark@Hye-Yuns-MacBook-Pro git % ls     
notebooks_vandv	sitcomtn-081	ts_config_ocs
hyeyunpark@Hye-Yuns-MacBook-Pro git % cd sitcomtn-081 
hyeyunpark@Hye-Yuns-MacBook-Pro sitcomtn-081 % ls
COPYRIGHT		_static			requirements.txt
LICENSE			conf.py			technote.toml
Makefile		index.rst		tox.ini
README.rst		local.bib
hyeyunpark@Hye-Yuns-MacBook-Pro sitcomtn-081 % git branch
* main
hyeyunpark@Hye-Yuns-MacBook-Pro sitcomtn-081 % git fetch
hyeyunpark@Hye-Yuns-MacBook-Pro sitcomtn-081 % git branch -al
* main
  remotes/origin/HEAD -> origin/main
  remotes/origin/main
  remotes/origin/tickets/SITCOM-918
hyeyunpark@Hye-Yuns-MacBook-Pro sitcomtn-081 % git checkout tickets/SITCOM-918 remotes/origin/tickets/SITCOM-918
error: pathspec 'tickets/SITCOM-918' did not match any file(s) known to git
error: pathspec 'remotes/origin/tickets/SITCOM-918' did not match any file(s) known to git
hyeyunpark@Hye-Yuns-MacBook-Pro sitcomtn-081 % git checkout -b tickets/SITCOM-918 remotes/origin/tickets/SITCOM-918
branch 'tickets/SITCOM-918' set up to track 'origin/tickets/SITCOM-918'.
Switched to a new branch 'tickets/SITCOM-918'
hyeyunpark@Hye-Yuns-MacBook-Pro sitcomtn-081 % ls
COPYRIGHT		_static			requirements.txt
LICENSE			conf.py			technote.toml
Makefile		index.md		tox.ini
README.rst		local.bib
hyeyunpark@Hye-Yuns-MacBook-Pro sitcomtn-081 % vi index.md
hyeyunpark@Hye-Yuns-MacBook-Pro sitcomtn-081 % vi index.md
hyeyunpark@Hye-Yuns-MacBook-Pro sitcomtn-081 % git switch tickets/SITCOM-1390
fatal: invalid reference: tickets/SITCOM-1390
hyeyunpark@Hye-Yuns-MacBook-Pro sitcomtn-081 % vi index.md                   
hyeyunpark@Hye-Yuns-MacBook-Pro sitcomtn-081 % vi index.md
hyeyunpark@Hye-Yuns-MacBook-Pro sitcomtn-081 % git add index.md 
hyeyunpark@Hye-Yuns-MacBook-Pro sitcomtn-081 % git commit -m "edit the part of topple block analysis"
[tickets/SITCOM-918 ee14635] edit the part of topple block analysis
 1 file changed, 3 insertions(+), 3 deletions(-)
hyeyunpark@Hye-Yuns-MacBook-Pro sitcomtn-081 % git push
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 391 bytes | 391.00 KiB/s, done.
Total 3 (delta 2), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
To https://github.com/lsst-sitcom/sitcomtn-081.git
   0d730ac..ee14635  tickets/SITCOM-918 -> tickets/SITCOM-918
hyeyunpark@Hye-Yuns-MacBook-Pro sitcomtn-081 % git branch
  main
* tickets/SITCOM-918
hyeyunpark@Hye-Yuns-MacBook-Pro sitcomtn-081 % vi index.md                                      
hyeyunpark@Hye-Yuns-MacBook-Pro sitcomtn-081 % git checkout -b tickets/SITCOM-1390 origin/tickets/SITCOM-1390
fatal: 'origin/tickets/SITCOM-1390' is not a commit and a branch 'tickets/SITCOM-1390' cannot be created from it
hyeyunpark@Hye-Yuns-MacBook-Pro sitcomtn-081 % git branch -al
  main
* tickets/SITCOM-918
  remotes/origin/HEAD -> origin/main
  remotes/origin/main
  remotes/origin/tickets/SITCOM-918
hyeyunpark@Hye-Yuns-MacBook-Pro sitcomtn-081 % git checkout tickets/SITCOM-1390
error: pathspec 'tickets/SITCOM-1390' did not match any file(s) known to git
hyeyunpark@Hye-Yuns-MacBook-Pro sitcomtn-081 % git branch tickets/SITCOM-1390
hyeyunpark@Hye-Yuns-MacBook-Pro sitcomtn-081 % git branch
  main
  tickets/SITCOM-1390
* tickets/SITCOM-918
hyeyunpark@Hye-Yuns-MacBook-Pro sitcomtn-081 % git checkout tickets/SITCOM-1390
Switched to branch 'tickets/SITCOM-1390'
hyeyunpark@Hye-Yuns-MacBook-Pro sitcomtn-081 % ls
COPYRIGHT		Makefile		_static			index.md		requirements.txt	tox.ini
LICENSE			README.rst		conf.py			local.bib		technote.toml
hyeyunpark@Hye-Yuns-MacBook-Pro sitcomtn-081 % git branh
git: 'branh' is not a git command. See 'git --help'.

The most similar command is
	branch
hyeyunpark@Hye-Yuns-MacBook-Pro sitcomtn-081 % git branch
  main
* tickets/SITCOM-1390
  tickets/SITCOM-918
hyeyunpark@Hye-Yuns-MacBook-Pro sitcomtn-081 % vi index.md  
hyeyunpark@Hye-Yuns-MacBook-Pro sitcomtn-081 % git add index.md                                              
hyeyunpark@Hye-Yuns-MacBook-Pro sitcomtn-081 % git commit -m "add figures for the topple block analysis"     
[tickets/SITCOM-1390 d084265] add figures for the topple block analysis
 1 file changed, 9 insertions(+)
hyeyunpark@Hye-Yuns-MacBook-Pro sitcomtn-081 % git push
fatal: The current branch tickets/SITCOM-1390 has no upstream branch.
To push the current branch and set the remote as upstream, use

    git push --set-upstream origin tickets/SITCOM-1390

To have this happen automatically for branches without a tracking
upstream, see 'push.autoSetupRemote' in 'git help config'.

hyeyunpark@Hye-Yuns-MacBook-Pro sitcomtn-081 % git branch
  main
* tickets/SITCOM-1390
  tickets/SITCOM-918
hyeyunpark@Hye-Yuns-MacBook-Pro sitcomtn-081 % git switch tickets/SITCOM-918
Switched to branch 'tickets/SITCOM-918'
Your branch is up to date with 'origin/tickets/SITCOM-918'.
hyeyunpark@Hye-Yuns-MacBook-Pro sitcomtn-081 % ls                                                       
COPYRIGHT		Makefile		_static			index.md		requirements.txt	tox.ini
LICENSE			README.rst		conf.py			local.bib		technote.toml
hyeyunpark@Hye-Yuns-MacBook-Pro sitcomtn-081 % vi index.md
hyeyunpark@Hye-Yuns-MacBook-Pro sitcomtn-081 % git switch tickets/SITCOM-1390
Switched to branch 'tickets/SITCOM-1390'
hyeyunpark@Hye-Yuns-MacBook-Pro sitcomtn-081 % git push --set-upstream origin tickets/SITCOM-1390
Enumerating objects: 48, done.
Counting objects: 100% (48/48), done.
Delta compression using up to 8 threads
Compressing objects: 100% (36/36), done.
Writing objects: 100% (45/45), 8.98 MiB | 2.81 MiB/s, done.
Total 45 (delta 13), reused 39 (delta 9), pack-reused 0
remote: Resolving deltas: 100% (13/13), completed with 1 local object.
remote: 
remote: Create a pull request for 'tickets/SITCOM-1390' on GitHub by visiting:
remote:      https://github.com/lsst-sitcom/sitcomtn-081/pull/new/tickets/SITCOM-1390
remote: 
To https://github.com/lsst-sitcom/sitcomtn-081.git
 * [new branch]      tickets/SITCOM-1390 -> tickets/SITCOM-1390
branch 'tickets/SITCOM-1390' set up to track 'origin/tickets/SITCOM-1390'.
hyeyunpark@Hye-Yuns-MacBook-Pro sitcomtn-081 % vi index.md                                       
hyeyunpark@Hye-Yuns-MacBook-Pro sitcomtn-081 % git add index.md                                    
hyeyunpark@Hye-Yuns-MacBook-Pro sitcomtn-081 % git commit -m "add figures for the topple block analysis"
[tickets/SITCOM-1390 5ee446d] add figures for the topple block analysis
 1 file changed, 4 insertions(+), 2 deletions(-)
hyeyunpark@Hye-Yuns-MacBook-Pro sitcomtn-081 % git push --set-upstream origin tickets/SITCOM-1390  
To https://github.com/lsst-sitcom/sitcomtn-081.git
 ! [rejected]        tickets/SITCOM-1390 -> tickets/SITCOM-1390 (fetch first)
error: failed to push some refs to 'https://github.com/lsst-sitcom/sitcomtn-081.git'
hint: Updates were rejected because the remote contains work that you do
hint: not have locally. This is usually caused by another repository pushing
hint: to the same ref. You may want to first integrate the remote changes
hint: (e.g., 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
hyeyunpark@Hye-Yuns-MacBook-Pro sitcomtn-081 % git fetch
remote: Enumerating objects: 13, done.
remote: Counting objects: 100% (12/12), done.
remote: Compressing objects: 100% (9/9), done.
remote: Total 9 (delta 3), reused 0 (delta 0), pack-reused 0 (from 0)
Unpacking objects: 100% (9/9), 1.06 MiB | 757.00 KiB/s, done.
From https://github.com/lsst-sitcom/sitcomtn-081
   d084265..a631aeb  tickets/SITCOM-1390 -> origin/tickets/SITCOM-1390
   ee14635..e2da1b8  tickets/SITCOM-918  -> origin/tickets/SITCOM-918
hyeyunpark@Hye-Yuns-MacBook-Pro sitcomtn-081 % git push                                          
To https://github.com/lsst-sitcom/sitcomtn-081.git
 ! [rejected]        tickets/SITCOM-1390 -> tickets/SITCOM-1390 (non-fast-forward)
error: failed to push some refs to 'https://github.com/lsst-sitcom/sitcomtn-081.git'
hint: Updates were rejected because the tip of your current branch is behind
hint: its remote counterpart. Integrate the remote changes (e.g.
hint: 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
hyeyunpark@Hye-Yuns-MacBook-Pro sitcomtn-081 % git pull
hint: You have divergent branches and need to specify how to reconcile them.
hint: You can do so by running one of the following commands sometime before
hint: your next pull:
hint: 
hint:   git config pull.rebase false  # merge
hint:   git config pull.rebase true   # rebase
hint:   git config pull.ff only       # fast-forward only
hint: 
hint: You can replace "git config" with "git config --global" to set a default
hint: preference for all repositories. You can also pass --rebase, --no-rebase,
hint: or --ff-only on the command line to override the configured default per
hint: invocation.
fatal: Need to specify how to reconcile divergent branches.
hyeyunpark@Hye-Yuns-MacBook-Pro sitcomtn-081 % vi index.md                                         

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

## Vibration due to the topple block

There are two topple blocks at az~-75 and az~-53 to detect the direction of the rotation in azimuth and to prevent TMA from slewing in one direction over the maximum angle of its rotation. While hitting the topple block and flipping it, it generates vibration and we have studied the vibration and the hardpoint forces fluctuating due to the topple blocks.

.. figure:: /_static/20231129_MTM1M3_vibration.png


.. figure::/_static/20231129_MTM1M3_zoomin.png



## Earthquake Response


[2023, 06, 27 - m1m3 test log]: https://confluence.lsstcorp.org/display/LSSTCOM/23.06.27+-+M1M3+Test+Log
[lvv-11306]: https://jira.lsstcorp.org/browse/LVV-11306
[sitcom-1089]: https://jira.lsstcorp.org/browse/SITCOM-1089

