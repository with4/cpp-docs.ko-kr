---
title: "컴파일러 오류 C3852 | Microsoft Docs"
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
  - "C3852"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3852"
ms.assetid: 194e5c5e-0dfb-414e-86db-791c11eb610c
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3852
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'member'\('type' 형식\): 집합체 초기화에서 이 멤버를 초기화할 수 없었습니다.  
  
 집합체 초기화로 기본 초기화를 받아들일 수 없는 데이터 멤버에 집합체 초기화의 일부로 기본 초기화를 할당하려고 했습니다.  
  
 다음 샘플에서는 C3852 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3852.cpp  
struct S  
{  
   short s;  
};  
  
struct S1  
{  
   int i;  
   const S s;  
};  
  
struct S2  
{  
   int i;  
   char & rc;  
};  
  
int main()  
{  
   S1 s1 = { 1 };   // C3852 const member   
   // try the following line instead  
   // S1 s1 = { 1, 2 };  
  
   S2 s2 = { 2 };   // C3852 reference member  
   // try the following line instead  
   // char c = 'a';  
   S2 s2 = { 2, c };  
}  
```