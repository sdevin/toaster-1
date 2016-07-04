# FAQ



## I'm using indigo and the 3d models in rviz are white.

This is an issue with the last version of rviz. A work around consist in installing hydro version.

```shell
> cd ${CATKIN_PATH}/src
> git clone -b hydro-devel https://github.com/ros-visualization/rviz.git
> cd ..
> catkin_make
```

## When using _agent_monitor_, nothing happens.

It may be due to boost conflict. See [this topic](http://answers.ros.org/question/173940/compiling-with-dynamic_reconfigure-server-code-leads-to-deadlock/) for details.

two solutions are possible: use hydro branch or go to `toaster/agent_monitor/src/main.cpp` and comment lines:

```javascript
ParamServer_t monitoring_dyn_param_srv;
monitoring_dyn_param_srv.setCallback(boost::bind(&dynParamCallback, _1, _2));
```