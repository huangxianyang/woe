woe
===

.. image:: https://travis-ci.org/justdoit0823/pywxclient.svg?branch=master
    :target: https://travis-ci.org/justdoit0823/pywxclient

version: 0.1.4

Tools for WoE Transformation mostly used in ScoreCard Model for credit rating
该工具用于WOE转换,主要用在评分模型以获得信用评级

Installation
安装方法
--------------------------------

We can simply use pip to install, as the following:

.. code-block:: bash

   $ pip install woe

or installing from git

.. code-block:: bash

   $ pip install git+https://github.com/boredbird/woe


Features
项目特性
========

  * Split tree with IV criterion

  * Rich and plentiful model eval methods

  * Unified format and easy for output

  * Storage of IV tree for follow-up use

  * 基于信息值IV进行数据离散化
  * 丰富的模型评估方法
  * 统一格式,易于输出
  * 存储IV树,以便后续使用

**woe** module function tree 项目文件及函数清单
============================

:: 

	|- __init__
	|- config.py 
	|   |-- config
	|   	|-- __init__
	|		|-- change_config_var_dtype()
	|		|-- load_file()
	|- eval.py 
	|   |-- compute_ks()
	|   |-- eval_data_summary()
	|   |-- eval_feature_detail()
	|   |-- eval_feature_stability()
	|   |-- eval_feature_summary()
	|   |-- eval_model_stability()
	|   |-- eval_model_summary()
	|   |-- eval_segment_metrics()
	|   |-- plot_ks()
	|   |-- proc_cor_eval()
	|   |-- proc_validation()
	|   |-- wald_test()
	|- feature_process.py 
	|   |-- binning_data_split()
	|   |-- calculate_iv_split()
	|   |-- calulate_iv()
	|   |-- change_feature_dtype()
	|   |-- check_point()
	|   |-- fillna()
	|   |-- format_iv_split()
	|   |-- proc_woe_continuous()
	|   |-- proc_woe_discrete()
	|   |-- process_train_woe()
	|   |-- process_woe_trans()
	|   |-- search()
	|   |-- woe_trans()
	|- ftrl.py 
	|   |-- FTRL()
	|   |-- LR()
	|- GridSearch.py 
	|   |-- fit_single_lr()
	|   |-- grid_search_lr_c()
	|   |-- grid_search_lr_c_main()
	|   |-- grid_search_lr_validation()


Examples
========

In the examples directory, there is a simple woe transformation program as tutorials.
在example目录中,有个简单的woe转换程序作为教程
Or you can write a more complex program with this `woe` package.
你也可以使用woe包写更多复杂的项目

Version Records 版本更迭
================
woe 0.1.4 2018-03-01
	* support py3

woe 0.1.3 2018-02-09

	* woe.feature_process.proc_woe_discrete(): fix bug when deal with discrete varibales 处理离散变量时修复bug
	* woe.eval.eval_feature_detail(): fix bug : utf-8 output file format utf-8格式输出
	* woe.GridSearch.grid_search_lr_c_main(): add function warper for convenience and high efficiency,添加整合容器提高效率
	* woe.GridSearch.grid_search_lr_c_validation(): monitor the ks performance of training sets and test sets on different 'c' 监控不同的超参C在训练集和测试上的ks值
	* supplement examples test scripts 补充示例测试脚本


woe 0.1.2 2017-12-05

	* woe.ftrl.FTRL(): add online learning module 添加在线学习模型

woe 0.1.1 2017-11-28

	* woe.config.load_file(): change param data_path to be optional  将param data_path更改为可选
	* woe.eval.eval_feature_stability(): fix bug : psi_dict['stability_index'] computation error #计算损失函数
	* woe.feature_process.change_feature_dtype(): add friendly tips when encounter a error #统计损失函数
	* woe.feature_process.calulate_iv(): refactor the code #计算iv
	* woe.feature_process.calculate_iv_split(): refactor the code #根据iv离散数据
	* woe.feature_process.binning_data_split(): reduce the number of len() function calls with __len__() and shape attributes;replace namedtuple with dict
	* woe.feature_process.fillna(): new added function to fill null value #添加缺失值处理函数
	* woe.GridSearch.grid_search_lr_c(): list of regularization parameter c specified inside the function is changed to the user specified #检索最优参数C
	
woe 0.0.9 2017-11-21

	* Add module : GridSearch for the search of optimal hyper parametric C in LogisticRegression #搜索最优参数C
	* Code refactoring: function compute_ks and plot_ks  #计算ks值
 
woe 0.0.8 2017-09-28

	* More flexible: cancel conditional restriction in function feature_process.change_feature_dtype() #改变特征类型
	* Fix bug: the wrong use of deepcopy in function feature_process.woe_trans() #woe转换 
	
woe 0.0.7 2017-09-19

	* Fix bug: eval.eval_feature_detail raises ValueError('arrays must all be same length')
	* Add parameter interface: alpha specified step learning rate ,default 0.01

How to Contribute
--------------------------------

Email me,1002937942@qq.com.
