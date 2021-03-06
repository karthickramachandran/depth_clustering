add_executable(show_objects_node show_objects_node.cpp)
target_link_libraries(show_objects_node
                      ros_bridge
                      image_labeler
                      projections
                      ground_remove
                      visualization
                      ${MY_QT_LIBRARIES}
                      ${Boost_LIBRARIES}
                      ${catkin_LIBRARIES}
                      ${PCL_LIBRARIES}
                      ${CMAKE_THREAD_LIBS_INIT})

add_executable(show_objects_node_ros show_objects_node_ros.cpp)
target_link_libraries(show_objects_node_ros
                      ros_bridge
                      ros_vis
                      image_labeler
                      projections
                      ground_remove
                      visualization
                      ${MY_QT_LIBRARIES}
                      ${Boost_LIBRARIES}
                      ${catkin_LIBRARIES}
                      ${PCL_LIBRARIES}
                      ${CMAKE_THREAD_LIBS_INIT})

add_executable(show_objects_moosmann_ros show_objects_moosmann_ros.cpp)
target_link_libraries(show_objects_moosmann_ros
                      ros_vis
                      identifiable
                      velodyne_utils
                      ros_bridge
                      image_labeler
                      projections
                      ground_remove
                      visualization
                      folder_reader
                      ${MY_QT_LIBRARIES}
                      ${Boost_LIBRARIES}
                      ${catkin_LIBRARIES}
                      ${PCL_LIBRARIES}
                      ${OpenCV_LIBS}
                      ${CMAKE_THREAD_LIBS_INIT})

if (${PCL_FOUND})
  add_executable(save_clusters_node save_clusters_node.cpp)
  target_link_libraries(save_clusters_node
                        ros_bridge
                        image_labeler
                        projections
                        ground_remove
                        cloud_saver
                        ${Boost_LIBRARIES}
                        ${catkin_LIBRARIES}
                        ${OpenCV_LIBS}
                        ${PCL_LIBRARIES})
endif()
