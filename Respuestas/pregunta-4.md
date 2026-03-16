db.sensores.updateOne(
    { sensor_id: "S500"},
    { $set: { temperatura: 25 } }
)