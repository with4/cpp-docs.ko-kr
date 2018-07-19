---
title: 링커 도구 오류 LNK2004 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2004
dev_langs:
- C++
helpviewer_keywords:
- LNK2004
ms.assetid: 07645371-e67b-4a2c-b0e0-dde24c94ef7e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2619ebc3fcf997574628354a951619cd18a81b46
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33314342"
---
# <a name="linker-tools-error-lnk2004"></a>링커 도구 오류 LNK2004
gp 관련 픽스업 오버플로를 '대상'; 간단한 섹션 'section'이 너무 크거나 범위를 벗어났습니다.  
  
 섹션 너무 큽니다.  
  
 이 오류를 해결 하려면 명시적으로 #pragma 섹션 (".sectionname", 읽기, 쓰기, long)을 통해 긴 섹션의 데이터를 게시 하 고 사용 하 여 간단한 섹션의 크기를 줄이려면 `__declspec(allocate(".sectionname"))` 데이터 정 및 선언에 있습니다.  예를 들면 다음과 같습니다.  
  
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
  
 Long 데이터 섹션에 할당 합니다 (8 바이트) 보다 큰 데이터 집합이 될 구조 자체에 논리적으로 그룹화 된 데이터를 이동할 수도 있습니다.  예를 들면 다음과 같습니다.  
  
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
  
 이 오류는 심각한 오류 다음 `LNK1165`합니다.