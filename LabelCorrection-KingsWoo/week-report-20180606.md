<style>
/* 第一列表格宽度 */
table th:nth-of-type(1){
width: 10%;
}
/* 第二列表格宽度 */
table th:nth-of-type(2){
width: 20%;
}
/* 第三列表格宽度 */
table th:nth-of-type(3){
width: 30%;
}
/* 第四列表格宽度 */
table th:nth-of-type(4){
width: 40%;
}
/*  ... ...  */ 
</style>

# 周报20180606

---

## 体检数据库中code筛选

	
|病种|相关代码|是否使用|备注|
|----|--------|:------:|----|
|糖尿病
||407153, 402364, 001463 |Y|明确诊断为糖尿病的代码
||404688 |N|尿糖偏高但未确诊为糖尿病
|肥胖
||407036
|高血糖
||409302，005703 |Y|明确有血糖偏高字样且为主要症状的代码
||407153, 402364, 001463 |Y|糖尿病代码，由于在记录为糖尿病后不会再记录血糖偏高，而高血糖包括糖尿病和前期，因此同样将这批代码判断为高血糖
|高血压
||407056， 000709, 006435 |Y|高血压
||407113 |Y|描述为血压增高，血压升高，数量大，拟算入高血压
||409117, 408143 |N|描述为血压略增高/偏高，拟不算入高血压内
||407395 |N|大约70%为高血压病史，不算入
|高血脂
||408110, 406158 |Y|高脂血症
||408989, 408605 |?|血脂异常
||407655 |?|极低密度脂蛋白增高
||001341 |?|低密度脂蛋白增高
||407070, 407032 |?|高甘油三酯
||404694 |?|总胆固醇降低
||404313 |?|高密度脂蛋白降低
||001704 |?|总胆固醇增高，高胆固醇血症
|高尿酸血症
||001351 |Y|高尿酸血症
||005702 |?|血尿酸增高
|脂肪肝
||406338, 407092  |Y|脂肪肝
||407156 |Y|不均匀脂肪肝
|肝功能异常
||407435 |Y|肝功能异常
|心律失常|*过杂，不考虑*
|肾功能异常
||407678 |Y|肾功能异常
||402561 |Y|肾功能不全
||402568 |Y|肾萎缩
|胆囊炎
||000564 |Y|胆囊炎
|胆囊结石 
||407656 |?|胆囊壁胆固醇结晶
||001397 |Y|胆囊结石
|胆囊息肉
||409097, 408746, 406254 |Y|胆囊息肉
||408745 |Y|胆囊多发息肉
|胃炎
||408839 |Y|慢性非萎缩性胃炎
||407340, 402304 |Y|慢性浅表性胃炎
||005883 |Y|慢性浅表萎缩性胃炎
||001643 |Y|慢性萎缩性胃炎
||001470 |Y|慢性胃炎
|淋巴结肿大|*部位过多，不考虑*
|甲状腺结节
||408177, 408172, 402691, 001622 |Y|甲状腺结节
||407453 |Y|甲状腺结节伴钙化
||407473, 407461 |?|甲状腺弥漫性病变

**存在问题在于，医生常常把在某个code的基础上附加诊断，于是附加的诊断就没有单独的code出现了，需要进一步拆分。**

---