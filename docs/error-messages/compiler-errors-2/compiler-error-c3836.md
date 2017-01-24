---
title: "컴파일러 오류 C3836 | Microsoft Docs"
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
  - "C3836"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3836"
ms.assetid: 254f851b-7b7d-4c34-a740-fcf72f6a636a
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3836
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

정적 생성자에는 멤버 이니셜라이저 목록을 사용할 수 없습니다.  
  
 관리되는 클래스는 멤버 초기화 목록을 사용하는 정적 생성자를 포함할 수 없습니다.  정적 클래스 생성자는 클래스 초기화를 수행하기 위해 공용 언어 런타임에 의해 호출되며 정적 데이터 멤버를 초기화합니다.  
  
 다음 샘플에서는 C3836 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3836a.cpp  
// compile with: /clr  
ref class M  
{  
   static int s_i;  
  
public:  
   static M() :  s_i(1234)   // C3836, delete initializer to resolve  
   {  
   }  
};  
  
int main()  
{  
}  
```  
  
 다음 샘플에서는 C3836 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3836b.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
  
__gc class M  
{  
   static int s_i;  
  
public:  
   static M() :  s_i(1234)   // C3836, delete initializer to resolve  
   {  
   }  
};  
  
int main()  
{  
}  
```