---
title: "컴파일러 경고 (수준 4) C4256 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4256"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4256"
ms.assetid: a755a32e-895a-4837-a2b5-4ea06b736798
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 4) C4256
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : 가상 기본을 갖는 클래스의 생성자에 '...'가 있습니다. 호출이 Visual C\+\+의 이전 버전과 호환되지 않을 수도 있습니다.  
  
 호환되지 않을 수도 있습니다.  
  
 다음 코드 예제를 참조하십시오.  S2::S2 생성자의 정의된다면 \(int i,... \) Visual C\+\+ 컴파일러 버전 7의 이전 버전을 사용 하 여 컴파일한 다음 예제에서는 현재 버전을 사용 하 여 컴파일되는 그러나, s 3에 대 한 생성자를 호출은 특별 한 경우의 호출 규칙 변경 때문에 제대로 작동 하지 않습니다.  둘 다 Visual C\+\+ 6.0으로 컴파일할 경우에는 줄임표\(...\)에 매개 변수를 전달하지 않아야 제대로 호출됩니다.  
  
 이 경고를 해결하려면  
  
1.  생성자에 줄임표\(...\)를 사용하지 않습니다.  
  
2.  이 클래스를 정의하거나 참조하는 라이브러리를 포함한 프로젝트의 구성 요소가 모두 현재 버전을 사용하여 빌드되었는지 확인한 다음 [warning](../../preprocessor/warning.md) pragma를 사용하여 경고를 사용 안 함 상태로 만듭니다.  
  
 다음 샘플에서는 C4256 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4256.cpp  
// compile with: /W4  
// #pragma warning(disable : 4256)  
struct S1  
{  
};  
  
struct S2: virtual public S1  
{  
   S2( int i, ... )    // C4256  
   {  
      i = 0;  
   }  
   /*  
   // try the following line instead  
   S2( int i)  
   {  
      i = 0;  
   }  
   */  
};  
  
void func1()  
{  
   S2 S3( 2, 1, 2 );   // C4256  
   // try the following line instead  
   // S2 S3( 2 );  
}  
  
int main()  
{  
}  
```