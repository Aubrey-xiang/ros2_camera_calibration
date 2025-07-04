^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Changelog for package image_view
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

3.0.3 (2022-01-24)
------------------
* [backport Humble] Removed cfg files related with ROS 1 parameters (`#911 <https://github.com/ros-perception/image_pipeline/issues/911>`_) (`#913 <https://github.com/ros-perception/image_pipeline/issues/913>`_)
  Removed cfg files related with ROS 1 parameters. Backport
  https://github.com/ros-perception/image_pipeline/pull/911
* [backport humble] enable autosize parameter in disparity view (`#875 <https://github.com/ros-perception/image_pipeline/issues/875>`_) (`#897 <https://github.com/ros-perception/image_pipeline/issues/897>`_)
  backport `#875 <https://github.com/ros-perception/image_pipeline/issues/875>`_
  Co-authored-by: Michael Ferguson <mfergs7@gmail.com>
* [backport humble] ROS 2: Add option to prepend timestamp to image filename in image_saver node (`#870 <https://github.com/ros-perception/image_pipeline/issues/870>`_) (`#885 <https://github.com/ros-perception/image_pipeline/issues/885>`_)
  backport `#870 <https://github.com/ros-perception/image_pipeline/issues/870>`_
* [backport humble] Add support for floating point fps (`#866 <https://github.com/ros-perception/image_pipeline/issues/866>`_) (`#877 <https://github.com/ros-perception/image_pipeline/issues/877>`_)
  Backport `#866 <https://github.com/ros-perception/image_pipeline/issues/866>`_
* [backport Humble] use cv::DestroyAllWindows (`#863 <https://github.com/ros-perception/image_pipeline/issues/863>`_) (`#864 <https://github.com/ros-perception/image_pipeline/issues/864>`_)
  This ports `#816 <https://github.com/ros-perception/image_pipeline/issues/816>`_ to ROS 2 and prevents weird exit conditions if you
  already closed the window
  backport https://github.com/ros-perception/image_pipeline/pull/863
  Co-authored-by: Michael Ferguson <mfergs7@gmail.com>
* Contributors: Alejandro Hernández Cordero

3.0.2 (2022-01-17)
------------------

3.0.0 (2022-04-29)
------------------
* Cleanup image_view.
* reformat for the uncrustify linter
* fix code style divergence
* reduce number of lines under 100
* print correct topics, remap according to ros2 capabilities, print help with correct ros2 syntax
* declare and get parameters for value replacement
* transport shoudl be used as a ros arg parameter
* use ros2 syntax
* transport should be use as a ros-arg parameter
* Fix image saver bug and time-based image saving
* replace ROSTIME
* Changing to RCL_SYSTEM_TIME
* Fix timestamp creation
* changes per comments
* fix for stereo_image_proc_tests
* Add maintainer (`#667 <https://github.com/ros-perception/image_pipeline/issues/667>`_)
* please linters
* Fix wrong usage of rclcpp::Duration constructor
* Contributors: Chris Lalancette, Erwin Lejeune, Ivan Santiago Paunovic, Jacob Perron, Lars Lorentz Ludvigsen, Patrick Musau

2.2.1 (2020-08-27)
------------------
* remove email blasts from steve macenski (`#596 <https://github.com/ros-perception/image_pipeline/issues/596>`_)
* [Foxy] Use ament_auto Macros (`#573 <https://github.com/ros-perception/image_pipeline/issues/573>`_)
* Contributors: Joshua Whitley, Steve Macenski

2.2.0 (2020-07-27)
------------------
* Replacing deprecated header includes with new HPP versions. (`#566 <https://github.com/ros-perception/image_pipeline/issues/566>`_)
* Opencv 3 compatibility (`#564 <https://github.com/ros-perception/image_pipeline/issues/564>`_)
  * Remove GTK from image_view.
  * Reinstate OpenCV 3 compatibility.
* Use newer 'add_on_set_parameters_callback' API (`#562 <https://github.com/ros-perception/image_pipeline/issues/562>`_)
  The old API was deprecated in Foxy and since removed in https://github.com/ros2/rclcpp/pull/1199.
* Contributors: Chris Lalancette, Jacob Perron, Joshua Whitley

* Patch boost failure in image_view (`#541 <https://github.com/ros-perception/image_pipeline/issues/541>`_)
  * Patch boost failure in image_view
  * remove ros2_deps from circle with new releases
  * readd deps
* Contributors: Steve Macenski

* Initial ROS2 commit.
* Contributors: Michael Carroll

1.12.23 (2018-05-10)
--------------------

1.12.22 (2017-12-08)
--------------------

1.12.21 (2017-11-05)
--------------------
* call namedWindow from same thread as imshow, need waitKay, now cvStartWindowThreads is null funciton on window_QT.h (`#279 <https://github.com/ros-perception/image_pipeline/issues/279>`_)
* Contributors: Kei Okada

1.12.20 (2017-04-30)
--------------------
* DisparityViewNodelet: fixed freeze (`#244 <https://github.com/ros-perception/image_pipeline/issues/244>`_)
* launch image view with a predefined window size (`#257 <https://github.com/ros-perception/image_pipeline/issues/257>`_)
* Remove python-opencv run_depend for image_view (`#270 <https://github.com/ros-perception/image_pipeline/issues/270>`_)
  The `python-opencv` dependency pulls in the system OpenCV v2.4 which is
  not required since the `image_view` package depends on `cv_bridge` which
  pulls in `opencv3` and `opencv3` provides the python library that
  `image_view` can use.
* Fix encoding error message (`#253 <https://github.com/ros-perception/image_pipeline/issues/253>`_)
  * Fix encoding error message
  * Update image_saver.cpp
  Allow compilation on older compilers
* Including stereo_msgs dep fixes `#248 <https://github.com/ros-perception/image_pipeline/issues/248>`_ (`#249 <https://github.com/ros-perception/image_pipeline/issues/249>`_)
* Add no gui mode to just visualize & publish with image_view (`#241 <https://github.com/ros-perception/image_pipeline/issues/241>`_)
* stere_view: fixed empty left, right, disparity windows with opencv3
* Apply value scaling to depth/float image with min/max image value
  If min/max image value is specified we just use it, and if not,
  - 32FC1: we assume depth image with meter metric, and 10[m] as the max range.
  - 16UC1: we assume depth image with milimeter metric, and 10 * 1000[mm] as the max range.
* Depends on cv_bridge 1.11.13 for CvtColorForDisplayOptions
  Close `#238 <https://github.com/ros-perception/image_pipeline/issues/238>`_
* fix doc jobs
  This is a proper fix for `#233 <https://github.com/ros-perception/image_pipeline/issues/233>`_
* address gcc6 build error
  With gcc6, compiling fails with `stdlib.h: No such file or directory`,
  as including '-isystem /usr/include' breaks with gcc6, cf.,
  https://gcc.gnu.org/bugzilla/show_bug.cgi?id=70129.
  This commit addresses this issue for this package in the same way
  it was addressed in various other ROS packages. A list of related
  commits and pull requests is at:
  https://github.com/ros/rosdistro/issues/12783
  Signed-off-by: Lukas Bulwahn <lukas.bulwahn@oss.bmw-carit.de>
* Contributors: Christopher Wecht, Kartik Mohta, Kei Okada, Kentaro Wada, Lukas Bulwahn, Leonard Gerard, Vincent Rabaud, cwecht, mryellow

1.12.19 (2016-07-24)
--------------------
* Add colormap option in video_recorder
* Merge pull request `#203 <https://github.com/ros-perception/image_pipeline/issues/203>`_ from wkentaro/video-recorder-timestamp
  [image_view] Stamped video output filename for video recorder
* bump version requirement for cv_bridge dep
  Closes `#215 <https://github.com/ros-perception/image_pipeline/issues/215>`_
* Request for saving image with start/end two triggers
* Stamped video output filename
  - _filename:=output.avi _stamped_filename:=false -> output.avi
  - _filename:=_out.avi _stamped_filename:=true -> 1466299931.584632829_out.avi
  - _filename:=$HOME/.ros/.avi _stamped_filename:=true -> /home/ubuntu/.ros/1466299931.584632829.avi
* Revert max_depth_range to default value for cvtColorForDisplay
* Contributors: Kentaro Wada, Vincent Rabaud

1.12.18 (2016-07-12)
--------------------
* Use image_transport::Subscriber aside from ros::Subscriber
* Refactor: Remove subscription of camera_info in video_recorder
* Add colormap options for displaying image topic
* Use CvtColorForDisplayOptions for cvtColorForDisplay
* Contributors: Kentaro Wada, Vincent Rabaud

1.12.17 (2016-07-11)
--------------------
* Fix timestamp to get correct fps in video_recorder
* Get correct fps in video_recorder.cpp
* Do dynamic scaling for float images
* Contributors: Kentaro Wada

1.12.16 (2016-03-19)
--------------------
* Remove code for roslib on .cfg files
  Closes `#185 <https://github.com/ros-perception/image_pipeline/issues/185>`_
* add cv::waitKey for opencv3 installed from source to fix freezing issue
* when no image is saved, do not save camera info
  When the images are not recorded because "save_all_image" is false and "save_image_service" is false, the frame count should not be incremented and the camera info should not be written to disk.
* Add std_srvs to catkin find_package()
* Contributors: Jeremy Kerfs, Jochen Sprickerhof, Kentaro Wada, Krishneel

1.12.15 (2016-01-17)
--------------------
* simplify the OpenCV dependency
* [image_view] Configure do_dynamic_scaling param with dynamic_reconfigure
* [image_view] Scale 16UC1 depth image
* fix compilation
* Extract images which are synchronized with message_filters
* [image_view] Show full path when failed to save image
* [image_view] Enable to specify transport with arg
* [image_view] feedback: no need threading for callback
* [image_view/image_view] Make as a node
* Added sensor_msgs::Image conversion to cv::Mat from rqt_image_view in
  order to be able to create videos from kinect depth images (cv_bridge
  currently doesn't support 16UC1 image encoding).
  Code adapted from:
  https://github.com/ros-visualization/rqt_common_plugins/blob/groovy-devel/rqt_image_view/src/rqt_image_view/image_view.cpp
* simplify OpenCV3 conversion
* use the color conversion for display from cv_bridge
* Contributors: Carlos Costa, Kentaro Wada, Vincent Rabaud

1.12.14 (2015-07-22)
--------------------
* reduce the differences between OpenCV2 and 3
* do not build GUIs on Android
  This fixes `#137 <https://github.com/ros-perception/image_pipeline/issues/137>`_
* Contributors: Vincent Rabaud

1.12.13 (2015-04-06)
--------------------

1.12.12 (2014-12-31)
--------------------
* Convert function to inline to avoid duplicates with image_transport
* Revert "remove GTK dependency"
  This reverts commit a6e15e796a40385fbbf8da05966aa47d179dcb46.
  Conflicts:
  image_view/CMakeLists.txt
  image_view/src/nodelets/disparity_nodelet.cpp
  image_view/src/nodes/stereo_view.cpp
* Revert "make sure waitKey is called after imshow"
  This reverts commit d13e3ed6af819459bca221ece779964a74beefac.
* Revert "brings back window_thread"
  This reverts commit 41a655e8e99910c13a3e7f1ebfdd083207cef76f.
* Contributors: Gary Servin, Vincent Rabaud

1.12.11 (2014-10-26)
--------------------
* brings back window_thread
  This fixes `#102 <https://github.com/ros-perception/image_pipeline/issues/102>`_ fully
* small optimizations
* add the image_transport parameter
* Contributors: Vincent Rabaud

1.12.10 (2014-09-28)
--------------------

1.12.9 (2014-09-21)
-------------------
* get code to compile with OpenCV3
  fixes `#96 <https://github.com/ros-perception/image_pipeline/issues/96>`_
* Contributors: Vincent Rabaud

1.12.8 (2014-08-19)
-------------------

1.12.6 (2014-07-27)
-------------------
* make sure waitKey is called after imshow
* remove GTK dependency
* small speedups
* Contributors: Vincent Rabaud

1.12.5 (2014-05-11)
-------------------
* image_view: Add depend on gtk2
* Contributors: Scott K Logan

1.12.4 (2014-04-28)
-------------------
* fixes `#65 <https://github.com/ros-perception/image_pipeline/issues/65>`_
* Contributors: Vincent Rabaud

1.12.3 (2014-04-12)
-------------------

1.12.2 (2014-04-08)
-------------------

1.12.1 (2014-04-06)
-------------------
* get proper opencv dependency
* Contributors: Vincent Rabaud

1.11.7 (2014-03-28)
-------------------
* Added requirement for core.
* Contributors: Jonathan J Hunt

1.11.3 (2013-10-06 20:21:55 +0100)
----------------------------------
- #41: allow image_saver to save image topics
- #40: use proper download URL
