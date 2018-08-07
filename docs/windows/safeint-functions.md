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
ms.openlocfilehash: b8a0475b5d3ba9053cd5d2df5ffd99ce9292ba8e
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39603457"
---
# <a name="safeint-functions"></a>SafeInt 함수
SafeInt 라이브러리의 인스턴스를 만들지 않고도 사용할 수 있는 여러 기능을 제공 합니다 [SafeInt 클래스](../windows/safeint-class.md)합니다. 정수 오버플로에서 단일 수학 연산을 보호 하려는 경우 이러한 함수를 사용할 수 있습니다. 여러 개의 산술 연산을 보호 하려는 경우 만들어야 **SafeInt** 개체입니다. 보다 효과적으로 만들 것 **SafeInt** 를 이러한 함수를 여러 번 사용 보다는 개체입니다.  
  
 이러한 함수를 사용 하면 먼저 동일한 형식으로 변환 하지 않고도 두 가지 유형의 매개 변수에서 수학 작업을 수행 하거나 비교할 수 있습니다.  
  
 이러한 각 함수는 두 가지 서식 파일 형식: `T` 고 `U`입니다. 이러한 각 유형의 부울, 문자 또는 정수 계열 형식 수 있습니다. 정수 계열 형식 수 서명 되거나 서명 되지 않은 및 8 비트에서 64 비트 크기입니다.  
  
## <a name="in-this-section"></a>섹션 내용  
  
|기능|설명|  
|--------------|-----------------|  
|[SafeAdd](../windows/safeadd.md)|두 숫자를 더하고 오버플로 방지 합니다.|  
|[SafeCast](../windows/safecast.md)|한 가지 유형의 다른 형식으로 매개 변수를 캐스팅합니다.|  
|[SafeDivide](../windows/safedivide.md)|두 숫자를 나누고를 0으로 나눈 으로부터 보호 합니다.|  
|[SafeEquals](../windows/safeequals.md), [SafeGreaterThan](../windows/safegreaterthan.md), [SafeGreaterThanEquals](../windows/safegreaterthanequals.md)를 [SafeLessThan](../windows/safelessthan.md)를 [SafeLessThanEquals](../windows/safelessthanequals.md)합니다 [ SafeNotEquals](../windows/safenotequals.md)|두 숫자를 비교합니다. 이러한 함수를 사용 하면 해당 유형을 변경 하지 않고 두 개의 서로 다른 형식의 숫자를 비교할 수 있습니다.|  
|[SafeModulus](../windows/safemodulus.md)|두 숫자에 대 한 나머지 작업을 수행합니다.|  
|[SafeMultiply](../windows/safemultiply.md)|두 숫자를 함께 곱하고 오버플로 방지 합니다.|  
|[SafeSubtract](../windows/safesubtract.md)|두 숫자를 빼고 오버플로 방지 합니다.|  
  
## <a name="related-sections"></a>관련 단원  
  
|단원|설명|  
|-------------|-----------------|  
|[SafeInt 클래스](../windows/safeint-class.md)|합니다 **SafeInt** 클래스입니다.|  
|[SafeIntException 클래스](../windows/safeintexception-class.md)|SafeInt 라이브러리 관련 예외 클래스입니다.|