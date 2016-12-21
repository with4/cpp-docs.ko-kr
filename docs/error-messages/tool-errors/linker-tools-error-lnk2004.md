---
title: "링커 도구 오류 LNK2004 | Microsoft Docs"
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
  - "LNK2004"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2004"
ms.assetid: 07645371-e67b-4a2c-b0e0-dde24c94ef7e
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 링커 도구 오류 LNK2004
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'target'에 대한 gp 관련 픽스업 오버플로. 간단한 섹션 'section'이\(가\) 너무 크거나 범위를 벗어났습니다.  
  
 섹션이 너무 큽니다.  
  
 이 오류를 해결하려면 \#pragma 섹션\(".sectionname", read, write, long\)을 통해 긴 섹션에 데이터를 명시적으로 배치하거나 데이터 정의와 선언에 `__declspec(allocate(".sectionname"))`을 사용하여 간단한 섹션의 크기를 줄입니다.  예를 들면 다음과 같습니다.  
  
```  
#pragma section(".data$mylong", read, write, long)  
__declspec(allocate(".data$mylong"))  
char    rg0[1] = { 1 };  
char    rg1[2] = { 1 };  
char    rg2[4] = { 1 };  
char    rg3[8] = { 1 };  
char    rg4[16] = { 1 };  
char    rg5[32] = { 1 };  
```  
  
 논리적으로 그룹화된 데이터를 해당 구조체에 옮겨 이 구조체가 8바이트보다 큰 데이터 컬렉션이 되면 컴파일러에서 이를 긴 데이터 섹션에 할당할 수도 있습니다.  예를 들면 다음과 같습니다.  
  
```  
// from this...  
int     w1  = 23;  
int     w2 = 46;  
int     w3 = 23*3;  
int     w4 = 23*4;  
  
// to this...  
struct X {  
    int     w1;  
    int     w2;  
    int     w3;  
    int     w4;  
} x  = { 23, 23*2, 23*3, 23*4 };  
  
```  
  
 이 오류 다음에는 심각한 오류인 `LNK1165`가 옵니다.