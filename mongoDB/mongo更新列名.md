db.viewpacsinterface.update({},{$rename:{"TO_DATE(PRINTDT,'YYYY-MM-DDHH24:MI:SS')":"PRINTDT"}},{multi:true})
