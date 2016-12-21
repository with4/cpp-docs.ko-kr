---
title: "BITMAPINFO 구조체 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "BITMAPINFO"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BITMAPINFO 구조체"
ms.assetid: a00caa49-e4df-419f-89a7-ab03c13a1b5b
caps.latest.revision: 15
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# BITMAPINFO 구조체
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`BITMAPINFO` 구조는 Windows 장치 독립적 비트맵 \(DIB\)에 대한 크기와 색상 정보를 정의합니다.  
  
## 구문  
  
```  
typedef struct tagBITMAPINFO {  
   BITMAPINFOHEADER bmiHeader;  
   RGBQUAD bmiColors[1];  
} BITMAPINFO;  
```  
  
#### 매개 변수  
 `bmiHeader`  
 장치 독립적 비트맵의 크기 및 색 형식에 대한 정보를 포함하는 [BITMAPINFOHEADER](http://msdn.microsoft.com/library/windows/desktop/dd183376)구조를 지정합니다.  
  
 `bmiColors`  
 비트맵에서 색을 정의 하는 [RGBQUAD](http://msdn.microsoft.com/library/windows/desktop/dd162938) 또는  `DWORD`  데이터 형식의 집합을 지정합니다.  
  
## 설명  
 장치 독립적 비트맵은 두 가지 부분으로 구성됩니다: 비트맵의 색상과 크기를 지정하는  `BITMAPINFO` 구조와 비트맵 픽셀을 지정하는 바이트의 배열.  배열의 비트는 함께 압축되어야 하지만, 각 스캐닝선은  `LONG`  경계의 끝을 0으로 채워야 합니다.  높이가 양수면 비트맵의 원점은 왼쪽 아래 모서리입니다.  높이가 음수면 원점은 왼쪽 위 모퉁이입니다.  
  
 *압축된 비트맵*은  `BITMAPINFO`  구조 바로 뒤의 바이트 배열에 있는 비트맵입니다.  압축된 비트맵은 단일 포인터에 의해 참조됩니다.  
  
 `BITMAPINFO`  구조체와  `BITMAPINFOHEADER`  및  `RGBQUAD`  구조체의 멤버에 대한 적절한 값에 대한 자세한 내용은 다음 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] 설명서의 항목을 참조하십시오.  
  
-   [\<caps:sentence id\="tgt11" sentenceid\="b5dd2e8c9cedbac12eb858bd01a029a2" class\="tgtSentence"\>BITMAPINFO 구조체\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/dd183375)  
  
-   [BITMAPINFOHEADER](http://msdn.microsoft.com/library/windows/desktop/dd183376) 구조  
  
-   [RGBQUAD](http://msdn.microsoft.com/library/windows/desktop/dd162938) 구조  
  
## 요구 사항  
 **Header:** wingdi.h  
  
## 참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CBrush::CreateDIBPatternBrush](../Topic/CBrush::CreateDIBPatternBrush.md)   
 [BITMAPINFOHEADER](http://msdn.microsoft.com/library/windows/desktop/dd183376)   
 [RGBQUAD](http://msdn.microsoft.com/library/windows/desktop/dd162938)