---
title: "컴파일러 오류 C3893 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3893"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3893"
ms.assetid: 90d52eae-6ef2-4db1-b7ad-92f9e8b140fb
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# 컴파일러 오류 C3893
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var' : 'type\_name' 클래스의 인스턴스 생성자에서만 initonly 데이터 멤버를 왼쪽 항의 값\(l\-value\)으로 사용할 수 있습니다.  
  
 정적 [initonly](../../dotnet/initonly-cpp-cli.md) 데이터 멤버의 주소는 정적 생성자에서만 사용할 수 있습니다.  
  
 인스턴스\(비정적\) initonly 데이터 멤버의 주소는 인스턴스\(비정적\) 생성자에서만 사용할 수 있습니다.  
  
 다음 샘플에서는 C3893 오류가 발생하는 경우를 보여 줍니다.  
  
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