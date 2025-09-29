# Leo-Muography-Analysis-FrameWork

## ScintillatorClass
此檔案包含一Class用以建立閃爍體物件。利用此Class建立的閃爍體物件，僅能從GeneralID建立。此類別包含五種方法：
- GetID()

  回傳此閃爍體的GenID
- GetInfo()         
  以tuple回傳此閃爍體的(GenID, 中心x座標, 中心y座標, 中心ｚ座標, LayerID)
- GetCenter()       
  以tuple回傳此閃爍體的(中心x座標, 中心y座標, 中心ｚ座標)
- GetVertices()     
  ndarray回傳此閃爍體的八個頂點。資料形狀為8*3的二維陣列

- line_cross_it_or_not(self, line_start, line_vec) 
  此方法需給予一點一方向向量決定一空間中的直線，判斷該直線是否穿過閃爍體。回傳值為一布林。line_start和line_vec都應該為tuple (x_0, y_0, z_0)和 (px, py, pz)





## 001_IDtoCoordinate





## 002_CombinationMaker




## 003_FromAbsoluteToTrlativeConfigs




## 004_Calculate_Solid_Angles
