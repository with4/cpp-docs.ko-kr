---
title: 컴파일러 오류 C2719 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2719
dev_langs:
- C++
helpviewer_keywords:
- C2719
ms.assetid: ea6236d3-8286-45cc-9478-c84ad3dd3c8e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ee8779db363c506d2f4ad884e15f78ba8231caa7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33233336"
---
# <a name="compiler-error-c2719"></a>컴파일러 오류 C2719
'parameter': __declspec(align('#'))를 사용하는 정식 매개 변수는 정렬되지 않습니다.  
  
 [맞춤](../../cpp/align-cpp.md) `__declspec` 한정자 함수 매개 변수에서 허용 되지 않습니다. 함수 매개 변수 맞춤은 사용되는 호출 규칙에 의해 제어됩니다. 자세한 내용은 참조 [호출 규칙](../../cpp/calling-conventions.md)합니다.  
  
 다음 샘플에서는 C2719 오류가 발생하는 경우 및 이를 해결하는 방법을 보여 줍니다.  
  
```  
// C2719.cpp  
void func(int __declspec(align(32)) i);   // C2719  
// try the following line instead  
// void func(int i);  
```