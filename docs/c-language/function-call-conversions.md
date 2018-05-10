---
title: 함수 호출 변환 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- function calls, converting
- function calls, argument type conversions
- functions [C], argument conversions
ms.assetid: 04ea0f81-509a-4913-8b12-0937a81babcf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 71b0fc4468ea98f04c87c8389021f2e12d9cae69
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="function-call-conversions"></a>함수 호출 변환
함수 호출의 인수에서 수행되는 변환 형식은 호출된 함수를 위해 선언된 인수 형식을 포함하는 함수 프로토타입(정방향 선언)의 존재 여부에 따라 달라집니다.  
  
 함수 프로토타입이 있고 선언된 인수 형식이 포함된 경우 컴파일러는 형식 확인을 수행합니다([함수](../c-language/functions-c.md) 참조).  
  
 함수 프로토타입이 없는 경우 함수 호출의 인수에 대해 일반 산술 변환만 수행됩니다. 이러한 변환은 호출의 각 인수에서 독립적으로 수행됩니다. 즉 **float** 값은 **double**로, `char` 또는 **short** 값은 `int`로, `unsigned char` 또는 **unsigned short**는 `unsigned int`로 변환됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [형식 변환](../c-language/type-conversions-c.md)