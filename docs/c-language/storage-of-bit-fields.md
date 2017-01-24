---
title: "비트 필드의 저장소 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
ms.assetid: 4816a241-1580-4d1c-82ed-13d359733959
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 비트 필드의 저장소
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**ANSI 3.5.2.1** int 내 비트 필드의 할당 순서  
  
 비트 필드는 최하위 비트에서 최상위 비트까지 정수 내에 할당됩니다.  다음 코드에서  
  
```  
struct mybitfields  
{  
   unsigned a : 4;  
   unsigned b : 5;  
   unsigned c : 7;  
} test;  
  
int main( void )  
{  
   test.a = 2;  
   test.b = 31;  
   test.c = 0;  
}  
```  
  
 비트는 다음과 같이 정렬됩니다.  
  
```  
00000001 11110010  
cccccccb bbbbaaaa  
```  
  
 80x86 프로세서는 높은 바이트 앞에 낮은 바이트의 정수 값을 저장하므로 0x01F2보다 높은 정수는 0x01이 뒤에 오는 0xF2로 실제 메모리에 저장됩니다.  
  
## 참고 항목  
 [구조체, 공용 구조체, 열거형 및 비트 필드](../c-language/structures-unions-enumerations-and-bit-fields.md)