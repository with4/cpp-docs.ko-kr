---
title: SafeInt 함수 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- functions, SafeInt
ms.assetid: fdc208e5-5d8a-41a9-8271-567fd438958d
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 97edd25abca3c9e80a35745165eedc93cc13a9b9
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="safeint-functions"></a>SafeInt 함수
SafeInt 라이브러리의 인스턴스를 만들지 않고 사용할 수 있는 여러 함수를 제공 된 [SafeInt 클래스](../windows/safeint-class.md)합니다. 정수 오버플로에서 단일 수학 연산을 보호 하려는 경우 이러한 함수를 사용할 수 있습니다. 여러 수학 연산을 보호 하려는 경우 만든 `SafeInt` 개체입니다. 것이 보다 효과적으로 만들 `SafeInt` 를 사용 하 여 이러한 함수가 여러 번 보다는 개체입니다.  
  
 이러한 함수를 사용 하 여 비교 하거나 먼저 동일한 형식으로 변환 하지 않고도 두 개의 서로 다른 유형의 매개 변수에서 수치 연산을 수행 합니다.  
  
 이러한 각 함수에는 두 템플릿 유형인: `T` 및 `U`합니다. 이러한 각 유형의 부울, 문자 또는 정수 계열 형식이 될 수 있습니다. 정수 계열 형식을 signed / unsigned 수 및 8 비트에서 64 비트로 크기입니다.  
  
## <a name="in-this-section"></a>섹션 내용  
  
|함수|설명|  
|--------------|-----------------|  
|[SafeAdd](../windows/safeadd.md)|두 숫자를 더하고 오버플로 방지 합니다.|  
|[SafeCast](../windows/safecast.md)|한 가지 유형의 다른 형식으로 매개 변수를 캐스팅합니다.|  
|[SafeDivide](../windows/safedivide.md)|두 숫자를 나누고 분모가 0을 방지 합니다.|  
|[SafeEquals](../windows/safeequals.md), [SafeGreaterThan](../windows/safegreaterthan.md), [SafeGreaterThanEquals](../windows/safegreaterthanequals.md), [SafeLessThan](../windows/safelessthan.md), [SafeLessThanEquals](../windows/safelessthanequals.md), [ SafeNotEquals](../windows/safenotequals.md)|두 숫자를 비교합니다. 이러한 함수를 사용 하 여 해당 형식을 변경 하지 않고 두 개의 다른 형식의 숫자를 비교할 수 있습니다.|  
|[SafeModulus](../windows/safemodulus.md)|두 숫자에 대해 모듈러스 연산을 수행합니다.|  
|[SafeMultiply](../windows/safemultiply.md)|두 숫자를 곱합니다 및 넘침을 방지 합니다.|  
|[SafeSubtract](../windows/safesubtract.md)|두 숫자를 빼고 오버플로 방지 합니다.|  
  
## <a name="related-sections"></a>관련 단원  
  
|단원|설명|  
|-------------|-----------------|  
|[SafeInt 클래스](../windows/safeint-class.md)|`SafeInt` 클래스|  
|[SafeIntException 클래스](../windows/safeintexception-class.md)|SafeInt 라이브러리에 특정 예외 클래스입니다.|