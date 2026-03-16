db.sensores.aggregate([
   { 
    $group: {
        _id: "$zona",
        temperatura_promedio: { $avg: "$temperatura" }
   }
},
{
    $project {
        _id: 0,
        zona: "$_id",
        temperatura_promedio: { $round:["$temperatura_promedio", 2] }
    }
},
{
    $sort: {zona: 1}
}
])