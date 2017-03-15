---
title: "컴파일러 경고 (수준 4) C4564 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4564"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4564"
ms.assetid: 555b301b-313e-4262-9f81-eb878674be60
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 경고 (수준 4) C4564
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'method' 메서드\(클래스 'class'에 있음\)는 지원되지 않는 기본 매개 변수 'parameter'을\(를\) 정의합니다.  
  
 컴파일러에서 기본값이 있는 매개 변수를 하나 이상 가진 메서드를 발견했습니다.  메서드를 호출할 때 매개 변수의 기본값은 무시되므로 이러한 매개 변수에 대한 값을 명시적으로 지정하십시오.  이러한 매개 변수의 값을 명시적으로 지정하지 않으면 C\+\+ 컴파일러에서는 오류를 발생시킵니다.  
  
 다음과 같이 Visual Basic으로 작성한 .dll에서는 메서드 인수에 기본 매개 변수를 사용할 수 있습니다.  
  
```  
' C4564.vb  
' compile with: vbc /t:library C4564.vb  
Public class TestClass  
   Public Sub MyMethod (a as Integer, _  
                        Optional c as Integer=1)  
   End Sub  
End class  
```  
  
 다음 C\+\+ 샘플에서는 Visual Basic으로 작성한 .dll을 사용합니다.  
  
```  
// C4564.cpp  
// compile with: /clr /W4 /WX  
#using <C4564.dll>  
  
int main() {  
   TestClass ^ myx = gcnew TestClass();   // C4564  
   myx->MyMethod(9);  
   // try the following line instead, to avoid an error  
   // myx->MyMethod(9, 1);  
}  
```