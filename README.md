# mongodb-tip

关联查询
db.orders.aggregate([{
	$lookup: {
		from: "product",     //被关联的集合
		localField: "pid",   //关联的字段
		foreignField: "_id", //被关联的字段
		as: "product",       //作为什么显示结果 
	}

}, {                    //过滤条件
	$match: {
		"ordername": "订单4"
	}
}])
