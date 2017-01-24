---
title: "필요한 값 계산 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "도우미 함수, 필요한 값 계산"
ms.assetid: 4f037d0f-881a-4a48-a9d2-9f8872dfccb7
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 필요한 값 계산
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

지연 도우미 루틴에서 계산해야 하는 두 가지 중요한 정보가 있습니다.  delayhlp.cpp에는 이 정보를 계산하는 데 사용되는 두 개의 인라인 함수가 있습니다.  
  
-   첫 번째 함수는 IAT\(가져오기 주소 테이블\), BIAT\(바인딩된 가져오기 주소 테이블\) 및 UIAT\(언바인딩된 가져오기 주소 테이블\)의 세 가지 테이블에서 현재 가져오기의 인덱스를 계산합니다.  
  
-   두 번째 함수는 유효한 IAT의 가져오기 수를 셉니다.  
  
```  
// utility function for calculating the index of the current import  
// for all the tables (INT, BIAT, UIAT, and IAT).  
__inline unsigned  
IndexFromPImgThunkData(PCImgThunkData pitdCur, PCImgThunkData pitdBase) {  
    return pitdCur - pitdBase;  
    }  
  
// utility function for calculating the count of imports given the base  
// of the IAT. NB: this only works on a valid IAT!  
__inline unsigned  
CountOfImports(PCImgThunkData pitdBase) {  
    unsigned        cRet = 0;  
    PCImgThunkData  pitd = pitdBase;  
    while (pitd->u1.Function) {  
        pitd++;  
        cRet++;  
        }  
    return cRet;  
    }  
```  
  
## 참고 항목  
 [Understanding the Helper Function](http://msdn.microsoft.com/ko-kr/6279c12c-d908-4967-b0b3-cabfc3e91d3d)