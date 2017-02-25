---
title: "CStrBufT Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CStrBufT<TCharType>"
  - "ATL.CStrBufT"
  - "CStrBufT"
  - "ATL::CStrBufT"
  - "ATL.CStrBufT<TCharType>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStrBufT class"
  - "shared classes, CStrBufT"
  - "문자열[C++], custom memory management"
ms.assetid: 6b50fa8f-87e8-4ed4-a229-157ce128710f
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# CStrBufT Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 자동 리소스 정리에 대 한 제공 `GetBuffer` 및 `ReleaseBuffer` 호출 하 여 기존 `CStringT` 개체입니다.  
  
## 구문  
  
```  
  
      template<  
   typename TCharType  
>  
class CStrBufT  
```  
  
#### 매개 변수  
 *TCharType*  
 문자 유형에 `CStrBufT` 클래스입니다.  다음 중 하나일 수 있습니다.  
  
-   `char`\(ANSI 문자 문자열\)  
  
-   `wchar_t`\(유니코드 문자 문자열\)  
  
-   **TCHAR** \(ANSI와 유니코드 문자열\)에 대 한  
  
## Members  
  
### 공용 Typedefs  
  
|Name|설명|  
|----------|--------|  
|`PCXSTR`|상수 문자열에 대 한 포인터입니다.|  
|`PXSTR`|문자열에 대 한 포인터입니다.|  
|`StringType`|버퍼는이 클래스 템플릿의 특수화가 조작할 수 있도록 되는 문자열 형식입니다.|  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CStrBufT::CStrBufT](../Topic/CStrBufT::CStrBufT.md)|문자열 버퍼 개체의 생성자입니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CStrBufT::SetLength](../Topic/CStrBufT::SetLength.md)|연결 된 문자열 개체의 문자 버퍼 길이 설정합니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CStrBufT::operator PCXSTR](../Topic/CStrBufT::operator%20PCXSTR.md)|검색은  **const** 연결 된 문자열 개체의 문자 버퍼에 대 한 포인터입니다.|  
|[CStrBufT::operator PXSTR](../Topic/CStrBufT::operator%20PXSTR.md)|연결 된 문자열 개체의 문자 버퍼에 대 한 포인터를 검색합니다.|  
  
### 공용 상수  
  
|Name|설명|  
|----------|--------|  
|[CStrBufT::AUTO\_LENGTH](../Topic/CStrBufT::AUTO_LENGTH.md)|새 릴리스를 문자열의 길이 자동으로 결정 합니다.|  
|[CStrBufT::SET\_LENGTH](../Topic/CStrBufT::SET_LENGTH.md)|GetBuffer 시 문자열 개체의 길이 설정|  
  
## 설명  
 이 클래스 래퍼 클래스 호출을 교체 하는 데 사용  [GetBuffer](../Topic/CSimpleStringT::GetBuffer.md) 및  [ReleaseBuffer](../Topic/CSimpleStringT::ReleaseBuffer.md), 또는  [GetBufferSetLength](../Topic/CSimpleStringT::GetBufferSetLength.md) 및 `ReleaseBuffer`.  
  
 주로 도우미 클래스로 설계 `CStrBufT` 개발자는 방법에 대 한 걱정을 하지 않고 문자열 개체의 문자 버퍼에 작업을 손쉽게 호출 하는 경우 또는 `ReleaseBuffer`.  이 예외가 발생 하거나 기존 여러 코드 경로가 경우 자연스럽 게 다루지 래퍼 개체를 거치 므로 가능 합니다. 문자열 리소스를 확보 하려면 소멸자가 발생 합니다.  
  
## 요구 사항  
 **헤더:** atlsimpstr.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [ATL\/MFC Shared Classes](../../atl-mfc-shared/atl-mfc-shared-classes.md)