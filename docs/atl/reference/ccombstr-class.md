---
title: "CComBSTR 클래스 | Microsoft Docs"
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
  - "ATL::CComBSTR"
  - "CComBSTR"
  - "ATL.CComBSTR"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BSTR, 래퍼"
  - "CComBSTR"
  - "CComBSTR 클래스"
ms.assetid: 8fea1879-a05e-47a5-a803-8dec60eaa534
caps.latest.revision: 21
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComBSTR 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 대 한 래퍼 클래스인 `BSTR`s.  
  
## 구문  
  
```  
  
class CComBSTR  
  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CComBSTR::CComBSTR](../Topic/CComBSTR::CComBSTR.md)|생성자입니다.|  
|[CComBSTR::~CComBSTR](../Topic/CComBSTR::~CComBSTR.md)|소멸자|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CComBSTR::Append](../Topic/CComBSTR::Append.md)|문자열에 추가 `m_str`.|  
|[CComBSTR::AppendBSTR](../Topic/CComBSTR::AppendBSTR.md)|Appends a `BSTR` to `m_str`.|  
|[CComBSTR::AppendBytes](../Topic/CComBSTR::AppendBytes.md)|지정한 수의 바이트를 추가 `m_str`.|  
|[CComBSTR::ArrayToBSTR](../Topic/CComBSTR::ArrayToBSTR.md)|만듭니다는 `BSTR` 에서 safearray에서 각 요소의 첫 번째 문자를 연결 하 고는 `CComBSTR` 개체.|  
|[CComBSTR::AssignBSTR](../Topic/CComBSTR::AssignBSTR.md)|Assigns a `BSTR` to `m_str`.|  
|[CComBSTR::Attach](../Topic/CComBSTR::Attach.md)|첨부는 `BSTR` 에 `CComBSTR` 개체입니다.|  
|[CComBSTR::BSTRToArray](../Topic/CComBSTR::BSTRToArray.md)|배열의 각 요소는 문자에서부터 1 차원 safearray를 만들고 있는 `CComBSTR` 개체입니다.|  
|[CComBSTR::ByteLength](../Topic/CComBSTR::ByteLength.md)|길이 반환 합니다. `m_str` \(바이트\)에서입니다.|  
|[CComBSTR::Copy](../Topic/CComBSTR::Copy.md)|복사본을 반환 합니다. `m_str`.|  
|[CComBSTR::CopyTo](../Topic/CComBSTR::CopyTo.md)|복사본을 반환 합니다. `m_str` 통해는  **\[out\]** 매개 변수|  
|[CComBSTR::Detach](../Topic/CComBSTR::Detach.md)|분리 `m_str` 에서 `CComBSTR` 개체입니다.|  
|[CComBSTR::Empty](../Topic/CComBSTR::Empty.md)|Frees `m_str`.|  
|[CComBSTR::Length](../Topic/CComBSTR::Length.md)|길이 반환 합니다. `m_str`.|  
|[CComBSTR::LoadString](../Topic/CComBSTR::LoadString.md)|문자열 리소스를 로드합니다.|  
|[CComBSTR::ReadFromStream](../Topic/CComBSTR::ReadFromStream.md)|로드는 `BSTR` 스트림에서 개체입니다.|  
|[CComBSTR::ToLower](../Topic/CComBSTR::ToLower.md)|문자열을 소문자로 변환 합니다.|  
|[CComBSTR::ToUpper](../Topic/CComBSTR::ToUpper.md)|문자열을 대문자로 변환 합니다.|  
|[CComBSTR::WriteToStream](../Topic/CComBSTR::WriteToStream.md)|저장 `m_str` 스트림을 합니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CComBSTR::operator BSTR](../Topic/CComBSTR::operator%20BSTR.md)|Casts a `CComBSTR` object to a `BSTR`.|  
|[CComBSTR::operator \!](../Topic/CComBSTR::operator%20!.md)|Returns `true` or `false`, depending on whether `m_str`is `NULL`.|  
|[CComBSTR::operator \!\=](../Topic/CComBSTR::operator%20!=.md)|비교는 `CComBSTR` 는 문자열을 사용 합니다.|  
|[CComBSTR::operator &](../Topic/CComBSTR::operator%20&.md)|반환 주소를 `m_str`.|  
|[CComBSTR::operator \+\=](../Topic/CComBSTR::operator%20+=.md)|추가 된 `CComBSTR` 개체입니다.|  
|[CComBSTR::operator \<](../Topic/CComBSTR::operator%20%3C.md)|비교는 `CComBSTR` 는 문자열을 사용 합니다.|  
|[CComBSTR::operator \=](../Topic/CComBSTR::operator%20=.md)|값으로 할당 `m_str`.|  
|[CComBSTR::operator \=\=](../Topic/CComBSTR::operator%20==.md)|비교는 `CComBSTR` 는 문자열을 사용 합니다.|  
|[CComBSTR::operator \>](../Topic/CComBSTR::operator%20%3E.md)|비교는 `CComBSTR` 는 문자열을 사용 합니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CComBSTR::m\_str](../Topic/CComBSTR::m_str.md)|포함의 `BSTR` 연관 된 `CComBSTR` 개체.|  
  
## 설명  
 `CComBSTR` 클래스에 대 한 래퍼는 `BSTR`s 길이 접두사가 문자열입니다.  길이 문자열에는 데이터 이전 메모리 위치를 정수로 저장 됩니다.  
  
 A  [BSTR](http://msdn.microsoft.com/ko-kr/1b2d7d2c-47af-4389-a6b6-b01b7e915228) null 종료\-마지막 문자 계산 되지만 문자열 안에 포함 된 null 문자를 포함할 수도 있습니다.  문자열 길이가 첫 번째 null 문자는 문자 수에 따라 결정 됩니다.  
  
> [!NOTE]
>  `CComBSTR` ANSI 또는 유니코드 문자열을 인수로 사용 하는 멤버 \(생성자, 대입 연산자 및 비교 연산자\)의 여러 클래스를 제공 합니다.  유니코드 문자열 임시 종종 내부적으로 생성 되기 때문에 이러한 함수의 ANSI 버전이 해당 유니코드 보다 덜 효율적입니다.  효율성을 위해 가능한 유니코드 버전을 사용 합니다.  
  
> [!NOTE]
>  Visual Studio.net에서 구현 되는 향상 된 조회 동작 때문에 같은 코드 `bstr = L"String2" + bstr;`에 이전 릴리스에서 컴파일된 수 대신 구현으로 `bstr = CStringW(L"String2") + bstr`.  
  
 사용 시 주의 사항 목록은 `CComBSTR`를 참조 하십시오  [Ccombstr와 프로그래밍](../../atl/programming-with-ccombstr-atl.md).  
  
## 요구 사항  
 **헤더:**  atlbase.h  
  
## 참고 항목  
 [Class Overview](../../atl/atl-class-overview.md)   
 [ATL and MFC String Conversion Macros](../Topic/ATL%20and%20MFC%20String%20Conversion%20Macros.md)