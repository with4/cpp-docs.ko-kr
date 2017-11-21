---
title: "컴파일러 오류 C2779 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2779
dev_langs: C++
helpviewer_keywords: C2779
ms.assetid: 4a00e492-855a-41f3-8a18-5f60ee20c2f2
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d0ef3215445e2245229407d41c7592b203cc1f70
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2779"></a>컴파일러 오류 C2779
'declaration': 속성 메서드만 비정적 데이터 멤버와 연결할 수  
  
 `property` 확장된 특성 정적 데이터 멤버에 올바르게 적용 됩니다.  
  
 다음 샘플에서는 C2779 오류가 생성 됩니다.  
  
```  
// C2779.cpp  
struct A {  
   static __declspec(property(put=PutProp))  
   // try the following line instead  
   __declspec(property(put=PutProp))  
      int prop;   // C2779  
   int PutProp(void);  
};  
```