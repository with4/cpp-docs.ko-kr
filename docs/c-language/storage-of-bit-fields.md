---
title: 비트 필드의 저장 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 4816a241-1580-4d1c-82ed-13d359733959
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3f223ff90517b6365645a861420ebe1985f994d2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32385047"
---
# <a name="storage-of-bit-fields"></a>비트 필드의 저장
**ANSI 3.5.2.1** int 내 비트 필드의 할당 순서  
  
 비트 필드는 최하위 비트에서 최상위 비트까지 정수 내에 할당됩니다. 다음 코드에서  
  
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
  
## <a name="see-also"></a>참고 항목  
 [구조체, 공용 구조체, 열거형 및 비트 필드](../c-language/structures-unions-enumerations-and-bit-fields.md)