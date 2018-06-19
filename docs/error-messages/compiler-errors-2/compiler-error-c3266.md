---
title: 컴파일러 오류 C3266 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3266
dev_langs:
- C++
helpviewer_keywords:
- C3266
ms.assetid: 7375c099-acb7-42f6-898d-57cfefa010b8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 52c6cc27c6724f5709ae4ded984afff23d16e19c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33247825"
---
# <a name="compiler-error-c3266"></a>컴파일러 오류 C3266
'class': 클래스-생성자에는 'void' 매개 변수 목록이 있어야 합니다.  
  
/clr 프로그래밍을 사용하는 클래스의 클래스-생성자는 매개 변수를 사용할 수 없습니다.  
  
다음 샘플에서는 C3266을 생성합니다.  
  
```  
// C3266.cpp  
// compile with: /clr  
  
ref class X {  
   static X(int i) { // C3266  
   // try the following line instead  
   // static X() {  
   }  
};  
  
int main() {  
}  
```  
