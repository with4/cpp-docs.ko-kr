---
title: "함수 호출 변환 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- function calls, converting
- function calls, argument type conversions
- functions [C], argument conversions
ms.assetid: 04ea0f81-509a-4913-8b12-0937a81babcf
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2cc3d425e3f9273dfc3ad1517aa441920057d70d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="function-call-conversions"></a>함수 호출 변환
함수 호출의 인수에서 수행되는 변환 형식은 호출된 함수를 위해 선언된 인수 형식을 포함하는 함수 프로토타입(정방향 선언)의 존재 여부에 따라 달라집니다.  
  
 함수 프로토타입이 있고 선언된 인수 형식이 포함된 경우 컴파일러는 형식 확인을 수행합니다([함수](../c-language/functions-c.md) 참조).  
  
 함수 프로토타입이 없는 경우 함수 호출의 인수에 대해 일반 산술 변환만 수행됩니다. 이러한 변환은 호출의 각 인수에서 독립적으로 수행됩니다. 즉 **float** 값은 **double**로, `char` 또는 **short** 값은 `int`로, `unsigned char` 또는 **unsigned short**는 `unsigned int`로 변환됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [형식 변환](../c-language/type-conversions-c.md)