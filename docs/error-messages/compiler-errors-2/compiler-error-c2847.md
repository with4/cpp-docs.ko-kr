---
title: 컴파일러 오류 C2847 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2847
dev_langs:
- C++
helpviewer_keywords:
- C2847
ms.assetid: 9ad9a0e0-8b16-49d9-a5be-f8eda2372aa9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cd18d685649c5ad8f03e3fdbb8b375717227f4c2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33245977"
---
# <a name="compiler-error-c2847"></a>컴파일러 오류 C2847
WinRT 또는 관리되는 형식 'class'에 sizeof를 적용할 수 없습니다.  
  
 [sizeof](../../cpp/sizeof-operator.md) 연산자는 컴파일 타임에 개체의 값을 가져옵니다. WinRT 또는 관리되는 클래스, 인터페이스 또는 값 형식의 크기는 동적이므로 컴파일 타임에 알 수 없습니다.  
  
 예를 들어 다음 샘플에서는 C2847 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2847.cpp  
// compile with: /clr  
ref class A {};  
  
int main() {  
   A ^ xA = gcnew A;  
   sizeof(*xA);   // C2847 cannot use sizeof on managed object  
}  
```  
