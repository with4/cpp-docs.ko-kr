---
title: "컴파일러 오류 C3174 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3174
dev_langs: C++
helpviewer_keywords: C3174
ms.assetid: fe6b3b5a-8196-485f-a45f-0b2e51df4086
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2dea7e564b7685cf58f9d97f15659d7f911817a6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3174"></a>컴파일러 오류 C3174
모듈 특성이 지정 되지 않았습니다.  
  
 Visual c + + 특성을 사용 하는 프로그램 사용 하지 않았습니다 고 [모듈](../../windows/module-cpp.md) 특성을 사용 하는 프로그램에 필요한는 특성입니다.  
  
 다음 샘플에서는 C3174 오류가 생성 됩니다.  
  
```  
// C3174.cpp  
// C3174 expected  
// uncomment the following line to resolve this C3174  
// [module(name="x")];  
[export]  
struct S  
{  
   int i;  
};  
  
int main()  
{  
}  
```