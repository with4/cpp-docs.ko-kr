---
title: __based 문법 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- based addressing
ms.assetid: a68ff750-c7fa-4c0c-8d5f-2df76e4686c5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 20e1c14cd7add01f8583c24541987b2980da794a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="based-grammar"></a>__based 문법
## <a name="microsoft-specific"></a>Microsoft 전용  
 기반 주소 지정은 개체가 할당된(정적 및 동적 기반 데이터) 세그먼트를 정밀하게 제어해야 할 때 유용합니다.  
  
 32비트와 64비트 컴파일이 호환되는 유일한 주소 지정 방식은 32비트/64비트 기반에 대해 32비트/64비트 치환을 포함하거나 `void`를 기반으로 하는 형식을 정의하는 "포인터 기반"입니다.  
  
## <a name="grammar"></a>문법  
 *범위 기반-한정자*:  
 **__based (***자료 식***)**   
  
 *기본 식*:  
 *based-variablebased-abstract-declaratorsegment-namesegment-cast*  
  
 *기반 변수*:  
 *identifier*  
  
 *기반-추상 선언 자*:  
 *추상 선언 자*  
  
 *기본 형식의*:  
 *type-name*  
  
**Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [기반 포인터](../cpp/based-pointers-cpp.md)