**VEX variables** present and accessible with vex expressions in many controller channel nodes:


* `v`: The incoming value
* `prev_v`: The previous input value
* `next_v`: The next input value
* `out_v`: The previous output value
* `aux_1_v`: The current sample value of the first aux input
* `aux_2_v`: The current sample value of the second aux input
* `aux_3_v`: The current sample value of the third aux input
* `i`: The sample index
* `cc_start`: The start time of the controller
* `cc_end`: The end time of the controller
* `cc_duration`: The duration of the controller
* `cc_grad`: The time progression gradient of the controller
* `abs_time`: The current sample's time in seconds
* `cc_min`: The minimum controller value
* `cc_max`: The maximum controller value
* `cc_len`: The sample count
* `cc_rate`: The controller point's sample rate
* `global_start`: The start time of all controller points
* `global_end`: The end time of all controller points
* `global_min`: The minimum value of all controller points
* `global_max`: The maximum value of all controller points
