---
title: "CComCurrency Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CComCurrency"
  - "ATL.CComCurrency"
  - "ATL::CComCurrency"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComCurrency class"
ms.assetid: a1c3d10a-bba6-40cc-8bcf-aed9023c8a9e
caps.latest.revision: 21
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComCurrency Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CComCurrency`에는 CURRENCY 개체를 만들고 관리하는 메서드 및 연산자가 있습니다.  
  
## 구문  
  
```  
  
class CComCurrency  
  
```  
  
## 멤버  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|[CComCurrency::CComCurrency](../Topic/CComCurrency::CComCurrency.md)|`CComCurrency` 개체에 대한 생성자입니다.|  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CComCurrency::GetCurrencyPtr](../Topic/CComCurrency::GetCurrencyPtr.md)|`m_currency` 데이터 멤버의 주소를 반환합니다.|  
|[CComCurrency::GetFraction](../Topic/CComCurrency::GetFraction.md)|`CComCurrency` 개체의 소수 부분을 반환하려면 이 메서드를 호출합니다.|  
|[CComCurrency::GetInteger](../Topic/CComCurrency::GetInteger.md)|`CComCurrency` 개체의 정수 부분을 반환하려면 이 메서드를 호출합니다.|  
|[CComCurrency::Round](../Topic/CComCurrency::Round.md)|`CComCurrency` 개체를 가장 가까운 정수 값으로 반올림하려면 이 메서드를 호출합니다.|  
|[CComCurrency::SetFraction](../Topic/CComCurrency::SetFraction.md)|`CComCurrency` 개체의 소수 부분을 설정하려면 이 메서드를 호출합니다.|  
|[CComCurrency::SetInteger](../Topic/CComCurrency::SetInteger.md)|`CComCurrency` 개체의 정수 부분을 설정하려면 이 메서드를 호출합니다.|  
  
### Public 연산자  
  
|이름|설명|  
|--------|--------|  
|[CComCurrency::operator \-](../Topic/CComCurrency::operator%20-2.md)|이 연산자는 `CComCurrency` 개체에 대해 빼기를 수행하는 데 사용됩니다.|  
|[CComCurrency::operator \!\=](../Topic/CComCurrency::operator%20!=.md)|두 `CComCurrency` 개체가 다른지 비교합니다.|  
|[CComCurrency::operator \*](../Topic/CComCurrency::operator%20*.md)|이 연산자는 `CComCurrency` 개체에 대해 곱하기를 수행하는 데 사용됩니다.|  
|[CComCurrency::operator \*\=](../Topic/CComCurrency::operator%20*=.md)|이 연산자는 `CComCurrency` 개체에 대해 곱하기를 수행하고 결과를 할당하는 데 사용됩니다.|  
|[CComCurrency::operator \/](../Topic/CComCurrency::operator%20-1.md)|이 연산자는 `CComCurrency` 개체에 대해 나누기를 수행하는 데 사용됩니다.|  
|[CComCurrency::operator \/\=](../Topic/CComCurrency::operator%20-=2.md)|이 연산자는 `CComCurrency` 개체에 대해 나누기를 수행하고 결과를 할당하는 데 사용됩니다.|  
|[CComCurrency::operator \+](../Topic/CComCurrency::operator%20+.md)|이 연산자는 `CComCurrency` 개체에 대해 더하기를 수행하는 데 사용됩니다.|  
|[CComCurrency::operator \+\=](../Topic/CComCurrency::operator%20+=.md)|이 연산자는 `CComCurrency` 개체에 대해 더하기를 수행하고 결과를 현재 개체에 할당하는 데 사용됩니다.|  
|[CComCurrency::operator \<](../Topic/CComCurrency::operator%20%3C.md)|이 연산자는 두 `CComCurrency` 개체를 비교하여 더 작은 값을 확인합니다.|  
|[CComCurrency::operator \<\=](../Topic/CComCurrency::operator%20%3C=.md)|이 연산자는 두 `CComCurrency` 개체를 비교하여 더 작거나 같은 값을 확인합니다.|  
|[CComCurrency::operator \=](../Topic/CComCurrency::operator%20=.md)|다음 연산자는 `CComCurrency` 개체에 새 값을 할당합니다.|  
|[CComCurrency::operator \-\=](../Topic/CComCurrency::operator%20-=1.md)|이 연산자는 `CComCurrency` 개체에 대해 빼기를 수행하고 결과를 할당하는 데 사용됩니다.|  
|[CComCurrency::operator \=\=](../Topic/CComCurrency::operator%20==.md)|이 연산자는 두 `CComCurrency` 개체가 같은지 비교합니다.|  
|[CComCurrency::operator \>](../Topic/CComCurrency::operator%20%3E.md)|이 연산자는 두 `CComCurrency` 개체를 비교하여 더 큰 값을 확인합니다.|  
|[CComCurrency::operator \>\=](../Topic/CComCurrency::operator%20%3E=.md)|이 연산자는 두 `CComCurrency` 개체를 비교하여 더 크거나 같은 값을 확인합니다.|  
|[CComCurrency::operator CURRENCY](../Topic/CComCurrency::operator%20CURRENCY.md)|`CURRENCY` 개체를 캐스트합니다.|  
  
### 공용 데이터 멤버  
  
|이름|설명|  
|--------|--------|  
|[CComCurrency::m\_currency](../Topic/CComCurrency::m_currency.md)|`CURRENCY` 변수는 클래스 인스턴스에 의해 만들어집니다.|  
  
## 설명  
 `CComCurrency`는 **CURRENCY** 데이터 형식의 래퍼입니다.  **CURRENCY**는 10,000 단위 배율의 8바이트 2의 보수 정수 값입니다.  소수점 기호 왼쪽에는 15자리 고정 소수점 번호가 있고 오른쪽에는 4자리 고정 소수점 번호가 있습니다.   **CURRENCY** 데이터 형식은 통화와 관련된 계산 또는 정확도가 중요한 모든 고정 소수점 계산에 특히 유용합니다.  
  
 **CComCurrency** 래퍼는 이 고정 소수점 형식에 대한 산술 연산, 할당 및 비교 작업을 구현합니다.  지원되는 응용 프로그램은 고정 소수점 계산 시 발생할 수 있는 반올림 오류를 제어하도록 선택했습니다.  
  
 `CComCurrency` 개체는 두 부분\(소수점 기호 왼쪽 값을 저장하는 정수 부분과 소수점 기호 오른쪽 값을 저장하는 소수 부분\)으로 된 소수점 기호의 한 쪽에 있는 숫자에 대한 액세스를 제공합니다.  소수 부분은 \-9999\(**CY\_MIN\_FRACTION**\)에서 \+9999\(**CY\_MAX\_FRACTION**\) 사이의 정수 값으로 내부적으로 저장됩니다.  [CComCurrency::GetFraction](../Topic/CComCurrency::GetFraction.md) 메서드는10000 단위 배율\(**CY\_SCALE**\)의 값을 반환합니다.  
  
 **CComCurrency** 개체의 정수 및 소수 부분을 지정할 때 소수 부분은 0~9999 범위의 숫자여야 합니다.  이는 소수점 뒤 두 자리의 유효 숫자만 사용하여 금액을 표현하는 미국 달러와 같은 통화를 처리할 때 중요합니다.  마지막 두 자리가 표시되지 않는 경우에도 이를 고려해야 합니다.  
  
|값|가능한 CComCurrency 할당|  
|-------|-------------------------|  
|$10.50|CComCurrency\(10,5000\) *또는* CComCurrency\(10.50\)|  
|$10.05|CComCurrency\(10,500\) *또는* CComCurrency\(10.05\)|  
  
 **CY\_MIN\_FRACTION**, **CY\_MAX\_FRACTION** 및 **CY\_SCALE** 값은 atlcur.h에 정의됩니다.  
  
## 요구 사항  
 **헤더:** atlcur.h  
  
## 참고 항목  
 [COleCurrency Class](../../mfc/reference/colecurrency-class.md)   
 [CURRENCY](http://msdn.microsoft.com/ko-kr/5e81273c-7289-45c7-93c0-32c1553f708e)   
 [Class Overview](../../atl/atl-class-overview.md)