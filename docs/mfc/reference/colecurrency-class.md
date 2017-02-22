---
title: "COleCurrency Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CURRENCY"
  - "COleCurrency"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleCurrency class"
  - "CURRENCY"
  - "fixed-point numbers"
  - "숫자, fixed-point"
ms.assetid: 3a36e345-303f-46fb-a57c-858274378a8d
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# COleCurrency Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

캡슐화는 `CURRENCY` OLE 자동화 데이터 형식입니다.  
  
## 구문  
  
```  
class COleCurrency  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[COleCurrency::COleCurrency](../Topic/COleCurrency::COleCurrency.md)|`COleCurrency` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[COleCurrency::Format](../Topic/COleCurrency::Format.md)|서식이 지정 된 문자열을 생성 하는 `COleCurrency` 개체입니다.|  
|[COleCurrency::GetStatus](../Topic/COleCurrency::GetStatus.md)|이 상태 \(유효\) 가져옵니다 `COleCurrency` 개체입니다.|  
|[COleCurrency::ParseCurrency](../Topic/COleCurrency::ParseCurrency.md)|읽기는  **통화** 문자열에서 값의 값을 설정 하 고 `COleCurrency`.|  
|[COleCurrency::SetCurrency](../Topic/COleCurrency::SetCurrency.md)|이 값은 설정 `COleCurrency` 개체입니다.|  
|[COleCurrency::SetStatus](../Topic/COleCurrency::SetStatus.md)|상태 \(유효\)을 설정 하는 `COleCurrency` 개체입니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[연산자 \=](../Topic/COleCurrency::operator%20=.md)|복사본은 `COleCurrency` 값입니다.|  
|[연산자 \+,\-](../Topic/COleCurrency::operator%20+,%20-.md)|추가 빼고 변경의 부호 `COleCurrency` 값입니다.|  
|[연산자 \+ \=, \=](../Topic/COleCurrency::operator%20+=,%20-=.md)|추가 하 고 빼는 `COleCurrency` 값이 `COleCurrency` 개체입니다.|  
|[연산자 \*, \/](../Topic/COleCurrency::operator%20*,%20-.md)|크기는 `COleCurrency` 값은 정수 값으로.|  
|[연산자 \* \=, \/ \=](../Topic/COleCurrency::operator%20*=,%20-=.md)|이 조정 `COleCurrency` 값은 정수 값으로.|  
|[연산자 \<\<](../Topic/COleCurrency::operator%20%3C%3C,%20%3E%3E.md)|Outputs a `COleCurrency` value to `CArchive` or `CDumpContext`.|  
|[연산자 \>\>](../Topic/COleCurrency::operator%20%3C%3C,%20%3E%3E.md)|입력 한 `COleCurrency` 개체에서 `CArchive`.|  
|[통화 연산자](../Topic/COleCurrency::operator%20CURRENCY.md)|변환 된 `COleCurrency` 값으로  **통화**.|  
|[연산자: \= \=, \<, \< \=, 등.](../Topic/COleCurrency%20Relational%20Operators.md)|두 비교 `COleCurrency` 값입니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[COleCurrency::m\_cur](../Topic/COleCurrency::m_cur.md)|기본 포함  **통화** 이 `COleCurrency` 개체입니다.|  
|[COleCurrency::m\_status](../Topic/COleCurrency::m_status.md)|이 상태를 포함 `COleCurrency` 개체입니다.|  
  
## 설명  
 **COleCurrency** 는 기본 클래스가 없습니다.  
  
 **통화** 는 8 바이트는 2의 보수 정수 값 10, 000으로 확장으로 구현 됩니다.  고정 소수점 숫자로 소수점 왼쪽으로 15 자리와 4 자리 숫자 오른쪽에 있습니다.  **통화** 데이터 형식인, 통화 관련 계산 이나 고정 소수점 계산에 대 한 매우 유용한 정확도 중요 합니다.  가능한 형식은 중 하나인는 `VARIANT` OLE 자동화 데이터 형식입니다.  
  
 **COleCurrency** 또한이 고정 소수점 형식에 대 한 몇 가지 기본적인 산술 연산을 구현 합니다.  고정 소수점 계산 중에 발생 하는 반올림 오류를 제어 하려면 지원 되는 작업 선택 했습니다.  
  
## 상속 계층 구조  
 `COleCurrency`  
  
## 요구 사항  
 **헤더:**  afxdisp.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [COleVariant Class](../../mfc/reference/colevariant-class.md)