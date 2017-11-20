---
title: "컴파일러 오류 C3734 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3734
dev_langs: C++
helpviewer_keywords: C3734
ms.assetid: 4e2afdcc-7da9-45a1-9c96-85f25e2986e8
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 83f523bb615ef06716f226d4a6c837acaa26c5b2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3734"></a>컴파일러 오류 C3734
'class': 관리되는 클래스 또는 WinRT 클래스에는 coclass를 사용할 수 없습니다.  
  
 [coclass](../../windows/coclass.md) 특성은 함께 사용할 수 없습니다 관리 되는 또는 WinRT 클래스입니다.  
  
 다음 샘플에서는 C3734를 생성하고 해결 방법을 보여 줍니다.  
  
```  
// C3734.cpp  
// compile with: /clr /c  
[module(name="x")];  
  
[coclass]  
ref class CMyClass {   // C3734 remove the ref keyword to resolve  
};  
```  
