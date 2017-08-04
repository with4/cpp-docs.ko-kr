---
title: "C 크기 조정 정수 형식 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- sized integer types
ms.assetid: 0d6199b4-d0ab-4e8c-a769-785f5afb92eb
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: db04c6862be26d5641a485c47ac7fd71b43d16fe
ms.contentlocale: ko-kr
ms.lasthandoff: 05/18/2017

---
# <a name="c-sized-integer-types"></a>C 크기 조정 정수 형식
**Microsoft 전용**  
  
 Microsoft C는 크기가 지정된 정수 형식을 지원합니다. __int*n* 형식 지정자를 사용하여 8비트, 16비트, 32비트 또는 64비트 정수 변수를 선언할 수 있습니다. 여기서 *n*은 정수 변수의 비트 크기입니다. *n*의 값은 8, 16, 32 또는 64입니다. 다음 예제에서는 네 가지 형식의 크기가 지정된 정수 각각의 변수 하나를 선언합니다.  
  
```  
__int8 nSmall;      // Declares 8-bit integer  
__int16 nMedium;    // Declares 16-bit integer  
__int32 nLarge;     // Declares 32-bit integer  
__int64 nHuge;      // Declares 64-bit integer  
```  
  
 처음 세 가지 형식의 크기가 지정된 정수는 크기가 같은 ANSI 형식에 대한 동의어이며 여러 플랫폼에서 동일하게 동작하는 이식 가능한 코드 작성에 유용합니다. __int8 데이터 형식은 char 형식과 동의어이고, \__int16은 short 형식과 동의어이며, \__int32는 int 형식과 동의어입니다. \__int64 형식에는 해당 ANSI 유형이 없습니다.  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [기본 형식의 저장소](../c-language/storage-of-basic-types.md)
