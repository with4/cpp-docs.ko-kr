---
title: "컴파일러 오류 C3893 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3893
dev_langs: C++
helpviewer_keywords: C3893
ms.assetid: 90d52eae-6ef2-4db1-b7ad-92f9e8b140fb
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4fee017305c90d9da69f5432815c0005eb84352c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
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