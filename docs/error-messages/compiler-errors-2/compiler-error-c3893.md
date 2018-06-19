---
title: 컴파일러 오류 C3893 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3893
dev_langs:
- C++
helpviewer_keywords:
- C3893
ms.assetid: 90d52eae-6ef2-4db1-b7ad-92f9e8b140fb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0c95d44a90b9325a492a0f179c941d46ff24030c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33273425"
---
# <a name="compiler-error-c3893"></a>컴파일러 오류 C3893
'var': 'type_name' 클래스의 인스턴스 생성자 에서만 initonly 데이터 멤버의 l 값 사용할 수는  
  
 정적 [initonly](../../dotnet/initonly-cpp-cli.md) 데이터 멤버는 정적 생성자에서의 주소를 하나만 사용할 수 있습니다.  
  
 인스턴스 (비정적) initonly 데이터 멤버의 주소 인스턴스 (비정적) 생성자를 하나만 사용할 수 있습니다.  
  
 다음 샘플에서는 C3893 오류가 생성 됩니다.  
  
```  
// C3893.cpp  
// compile with: /clr  
ref struct Y1 {  
   Y1() : data_var(0) {  
      int% i = data_var;   // OK  
   }  
   initonly int data_var;  
};  
  
int main(){  
   Y1^ y= gcnew Y1;  
   int% i = y->data_var;   // C3893  
}  
```