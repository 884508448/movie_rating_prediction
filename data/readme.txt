【文件说明】
	文件名称为"a_b_c.csv"
	a表示是训练集还是测试集，b表示数据划分时训练集占比，c表示划分训练集时采用随机采样还是分层采样
	例如：“test_1_fenceng.csv”与“train_1_fenceng.csv”为一组数据，对数据集进行分层采样，且训练集与测试集比例为9:1

【属性说明】
	一共有16个列：tconst、startYear、runtimeMinutes、averageRating、numVotes、region、writer_weight、director_weight、editor_weight、actor_weight、producer_weight、cinematographer_weight、composer_weight、genres_weight、sim_rating、boxoffice
	tconst：电影编号
	startYear：电影年份——目前记录的是原始数值，可以根据需要进行编号处理
	runtimeMinutes：电影时长（分钟）——目前记录的是原始数值，可以根据需要进行编号处理
	averageRating：电影评分
	numVotes：电影评分人数 ——目前记录的是原始数值，可以根据需要进行编号处理
	region：电影不同国家版本数量——对“akas.csv”中“region”进行统计
	writer_weight：编剧权重——该电影所有writer在训练集电影中作为writer的电影评分均值
	director_weight、editor_weight、actor_weight、producer_weight、cinematographer_weight、composer_weight：同上
	genres_weight：电影类型权重——该电影的所有类型在该电影中的重要性(tf-idf)*该类型电影的评分人数*该类型电影的平均评分/该电影的所有类型总的评分人数
	sim_rating：最相似的20部电影均分——根据电影简介利用tf-idf计算相似的20部电影并计算均分，若没有则用平均值代替
	boxoffice：电影票房——目前记录的是原始数值，可以根据需要进行编号处理

	