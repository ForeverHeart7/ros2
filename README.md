# ros2 导航调参

#重要参数
#1 costmap_common_params.yaml 文件
  robot_radius: 0.15    #机器人半径
  cost_scaling_factor:  15.0  #障碍物膨胀比例系数，全局路径呈锯齿状时调大
  inflation_radius:     0.2      #膨胀半径，全局路径离障碍太近时调大，但不能覆盖整个道路
#cost_scaling_factor调大，全局路径更平滑，inflation_radius根据情况适当调大

#2 teb_local_planner_params.yaml 文件
    #与障碍物相关
    min_obstacle_dist: 0.3   #与障碍的最小期望距离
    inflation_dist: 0.5 # 障碍物周围缓冲区
    dynamic_obstacle_inflation_dist: 0.6  #与动态障碍物缓冲区
    max_global_plan_lookahead_dist: 1.0 #向前规划最长距离 #太大路径不平滑，太小避障和转弯时效果不好，太小还会导致小车不敢走
    weight_optimaltime: 3 # 根据转换/执行时间对轨迹进行收缩的优化权重  #很重要的一个参数，值越大小车越大胆，转弯切内道，越容易拉到最大速度，也撞死得越快
#max_global_plan_lookahead_dist从小开始（使局部路径较贴近去全局路径），找最佳值
#weight_optimaltime小车卡住时，可适当调大

#以上为一些关键参数调整，具体见博客https://blog.csdn.net/qq_42406643/article/details/118754093?ops_request_misc=&request_id=&biz_id=102&utm_term=ros2%E5%AF%BC%E8%88%AA%E8%B0%83%E5%8F%82&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduweb~default-2-118754093.nonecase&spm=1018.2226.3001.4187

由于github不是很会熟练运用，更多笔记资料等可以去我的csdn博客看用户名：foreverheart7
