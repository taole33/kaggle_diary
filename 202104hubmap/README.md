このコンペの目的

Your challenge is to detect functional tissue units (FTUs) across different tissue preparation pipelines. An FTU is defined as a “three-dimensional block of cells centered around a capillary, such that each cell in this block is within diffusion distance from any other cell in the same block” (de Bono, 2013). The goal of this competition is the implementation of a successful and robust glomeruli FTU detector.  
  
あなたの課題は、さまざまな組織準備パイプライン全体で機能組織ユニット（FTU）を検出することです。 FTUは、「毛細血管を中心とするセルの3次元ブロックであり、このブロック内の各セルが同じブロック内の他のセルから拡散距離内にある」と定義されています（de Bono、2013）。この競争の目標は、成功した堅牢な糸球体FTU検出器の実装です。  
  
  
  
●ラベルのミスについて、コメントで言及あり。  
対処する必要あり  
https://www.kaggle.com/c/hubmap-kidney-segmentation/discussion/198116  
  
  
  
●ラベルが少しシフトしてて、それを修正しないといけないみたい。  
（古い情報の可能性あり。datasetが修正されていないか確認。）  
https://www.kaggle.com/c/hubmap-kidney-segmentation/discussion/201816   
  
  
●やることメモ  
・アンサンブルと、アンサンブルの元データ作り  
・import albumentations as A  

