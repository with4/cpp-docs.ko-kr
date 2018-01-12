---
title: "컴파일러 오류 C2844 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2844
dev_langs: C++
helpviewer_keywords: C2844
ms.assetid: dcaf4cd2-21b0-4280-ae42-0a706c524d83
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3353a6dbacaca2779bb4feffe55958baf0c944e8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2844"></a>컴파일러 오류 C2844
'member': ' interface '인터페이스의 멤버일 수 없습니다  
  
 [인터페이스 클래스](../../windows/interface-class-cpp-component-extensions.md) 속성 아닌 데이터 멤버를 포함할 수 없습니다.  
  
 속성 또는 멤버 함수 이외 인터페이스에는 허용 되지 않습니다. 또한 생성자, 소멸자 및 연산자 허용 되지 않습니다.  
  
 다음 샘플에서는 C2844 오류가 생성 됩니다.  
  
```  
// C2844a.cpp  
// compile with: /clr /c  
public interface class IFace {  
   int i;   // C2844  
   // try the following line instead  
   // property int Size;  
};  
```  
