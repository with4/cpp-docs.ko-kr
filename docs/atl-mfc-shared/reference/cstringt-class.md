---
title: "CStringT Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CString"
  - "CStringT"
  - "ATL::CStringT"
  - "ATL.CStringT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStringT class"
  - "shared classes, CStringT"
  - "문자열[C++], ATL"
ms.assetid: 7cacc59c-425f-40f1-8f5b-6db921318ec9
caps.latest.revision: 33
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 34
---
# CStringT Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스를 나타내는 한 `CStringT` 개체입니다.  
  
## 구문  
  
```  
  
      template< typename   
      BaseType  
      , class   
      StringTraits  
       >  
class CStringT :   
public CSimpleStringT<   BaseType,   _CSTRING_IMPL_::_MFCDLLTraitsCheck<      BaseType,      StringTraits   >   ::c_bIsMFCDLLTraits>  
```  
  
#### 매개 변수  
 `BaseType`  
 문자 형식 문자열 클래스입니다.  다음 중 하나일 수 있습니다.  
  
-   `char`\(ANSI 문자열에 대 한\).  
  
-   `wchar_t`\(유니코드 문자열에 대 한\).  
  
-   **TCHAR** \(ANSI와 유니코드 문자열\)에 대 한.  
  
 `StringTraits`  
 문자열 클래스 C 런타임 \(CRT\) 라이브러리 지원 및 문자열 리소스가 위치한 해야 하는지 결정 합니다.  다음 중 하나일 수 있습니다.  
  
-   **StrTraitATL \< wchar\_t** &#124; `char` &#124; **ChTraitsCRT, TCHAR \< wchar\_t** &#124; `char` &#124; **TCHAR \> \>**  
  
     리소스 문자열에 의해 지정 된 모듈에 대 한 검색 및 CRT 지원 클래스에 필요한 `m_hInstResource` \(응용 프로그램의 모듈 클래스의 멤버\).  
  
-   **StrTraitATL \< wchar\_t** &#124; `char` &#124; **ChTraitsOS, TCHAR \< wchar\_t** &#124; `char` &#124; **TCHAR \> \>**  
  
     클래스 CRT 지원 및 리소스 문자열에서 지정 된 모듈에 대 한 검색 하지 않아도 `m_hInstResource` \(응용 프로그램의 모듈 클래스의 멤버\).  
  
-   **StrTraitMFC \< wchar\_t** &#124; `char` &#124; **ChTraitsCRT, TCHAR \< wchar\_t** &#124; `char` &#124; **TCHAR \> \>**  
  
     클래스 지원 CRT 및 표준 MFC 검색 알고리즘을 사용 하 여 리소스 문자열을 검색 해야 합니다.  
  
-   **StrTraitMFC \< wchar\_t** &#124; `char` &#124; **ChTraitsOS, TCHAR \< wchar\_t** &#124; `char` &#124; **TCHAR \> \>**  
  
     클래스 지원 CRT 및 표준 MFC 검색 알고리즘을 사용 하 여 리소스 문자열에 대 한 검색 하지 않아도 됩니다.  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CStringT::CStringT](../Topic/CStringT::CStringT.md)|생성 된 `CStringT` 개체에서 다양 한 방법으로.|  
|[CStringT::~CStringT](../Topic/CStringT::~CStringT.md)|`CStringT` 개체를 소멸시킵니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CStringT::AllocSysString](../Topic/CStringT::AllocSysString.md)|할당 된 `BSTR` 에서 `CStringT` 데이터.|  
|[CStringT::AnsiToOem](../Topic/CStringT::AnsiToOem.md)|ANSI 문자 집합을 OEM 문자 집합에는 내부 변환이 됩니다.|  
|[CStringT::AppendFormat](../Topic/CStringT::AppendFormat.md)|서식이 지정 된 데이터는 기존 추가 `CStringT` 개체입니다.|  
|[CStringT::Collate](../Topic/CStringT::Collate.md)|\(대\/소문자 구분, 로캘별 정보 사용\) 두 문자열을 비교 합니다.|  
|[CStringT::CollateNoCase](../Topic/CStringT::CollateNoCase.md)|\(대\/소문자 구분 안함, 로캘별 정보 사용\) 두 문자열을 비교 합니다.|  
|[CStringT::Compare](../Topic/CStringT::Compare.md)|\(대 소문자 구분\) 두 문자열을 비교 합니다.|  
|[CStringT::CompareNoCase](../Topic/CStringT::CompareNoCase.md)|\(소문자\) 두 문자열을 비교 합니다.|  
|[CStringT::Delete](../Topic/CStringT::Delete.md)|문자열에서 하나 이상의 문자를 삭제합니다.|  
|[CStringT::Find](../Topic/CStringT::Find.md)|문자 또는 큰 문자열 내의 부분 문자열을 찾습니다.|  
|[CStringT::FindOneOf](../Topic/CStringT::FindOneOf.md)|첫 번째 일치 하는 문자를 집합을 찾습니다.|  
|[CStringT::Format](../Topic/CStringT::Format.md)|형식 문자열을 `sprintf` 하지.|  
|[CStringT::FormatMessage](../Topic/CStringT::FormatMessage.md)|메시지 문자열의 형식을 지정 합니다.|  
|[CStringT::FormatMessageV](../Topic/CStringT::FormatMessageV.md)|가변 인수 목록을 사용 하는 메시지 문자열의 형식을 지정 합니다.|  
|[CStringT::FormatV](../Topic/CStringT::FormatV.md)|가변 인수 목록을 사용 하 여 문자열의 형식을 지정 합니다.|  
|[CStringT::GetEnvironmentVariable](../Topic/CStringT::GetEnvironmentVariable.md)|지정한 환경 변수의 값을 설정 하는 문자열입니다.|  
|[CStringT::Insert](../Topic/CStringT::Insert.md)|단일 문자 또는 부분 문자열 내에서 지정 된 인덱스에 삽입합니다.|  
|[CStringT::Left](../Topic/CStringT::Left.md)|문자열의 왼쪽된 부분을 추출합니다.|  
|[CStringT::LoadString](../Topic/CStringT::LoadString.md)|기존 로드 `CStringT` Windows 리소스에서 개체입니다.|  
|[CStringT::MakeLower](../Topic/CStringT::MakeLower.md)|모든 문자를이 문자열을 소문자로 변환 합니다.|  
|[CStringT::MakeReverse](../Topic/CStringT::MakeReverse.md)|문자열을 취소합니다.|  
|[CStringT::MakeUpper](../Topic/CStringT::MakeUpper.md)|이 문자열을 대문자로 모든 문자를 변환 합니다.|  
|[CStringT::Mid](../Topic/CStringT::Mid.md)|문자열 중간 부분을 추출합니다.|  
|[CStringT::OemToAnsi](../Topic/CStringT::OemToAnsi.md)|OEM 문자 집합을 ANSI 문자 집합에는 현재 위치에서 변환이 됩니다.|  
|[CStringT::Remove](../Topic/CStringT::Remove.md)|제거 문자열에서에서 문자를 표시 합니다.|  
|[CStringT::Replace](../Topic/CStringT::Replace.md)|대체 문자를 다른 문자로 표시 합니다.|  
|[CStringT::ReverseFind](../Topic/CStringT::ReverseFind.md)|큰 문자열 안의 문자는 찾지 않습니다. 끝 부분에서 시작 합니다.|  
|[CStringT::Right](../Topic/CStringT::Right.md)|문자열의 오른쪽 부분을 추출합니다.|  
|[CStringT::SetSysString](../Topic/CStringT::SetSysString.md)|기존 설정 `BSTR` 개체에서 데이터는 `CStringT` 개체입니다.|  
|[CStringT::SpanExcluding](../Topic/CStringT::SpanExcluding.md)|식별 되는 문자 집합에 없는 첫 번째 문자에서 시작 하 여 문자열에서 문자를 추출 `pszCharSet`.|  
|[CStringT::SpanIncluding](../Topic/CStringT::SpanIncluding.md)|문자 집합에만 있는 부분 문자열을 추출 합니다.|  
|[CStringT::Tokenize](../Topic/CStringT::Tokenize.md)|추출 대상 문자열에서 토큰을 지정합니다.|  
|[CStringT::Trim](../Topic/CStringT::Trim.md)|모든 선행 및 후행 공백 문자는 문자열에서 트리밍합니다.|  
|[CStringT::TrimLeft](../Topic/CStringT::TrimLeft.md)|문자열에서 선행 공백 문자를 트림 합니다.|  
|[CStringT::TrimRight](../Topic/CStringT::TrimRight.md)|후행 공백 문자는 문자열에서 트림 합니다.|  
  
### 연산자  
  
|||  
|-|-|  
|[CStringT::operator \=](../Topic/CStringT::operator%20=.md)|새 값에 지정 된 `CStringT` 개체.|  
|[CStringT::operator \+](../Topic/CStringT::operator%20+.md)|두 문자열 또는 문자 및 문자열을 연결합니다.|  
|[CStringT::operator \+\=](../Topic/CStringT::operator%20+=.md)|기존 문자열의 끝에 새 문자열을 연결합니다.|  
|[CStringT::operator \=\=](../Topic/CStringT::operator%20==.md)|논리적으로 동일한 두 문자열이 있는지 확인 합니다.|  
|[CStringT::operator \!\=](../Topic/CStringT::operator%20!=.md)|두 문자열이 다르면 논리적으로 결정 합니다.|  
|[CStringT::operator \<](../Topic/CStringT::operator%20%3C.md)|미만으로 연산자의 왼쪽에 문자열 인지 여부를 확인 오른쪽에 있는 문자열입니다.|  
|[CStringT::operator \>](../Topic/CStringT::operator%20%3E.md)|문자열 연산자는 왼쪽에서 오른쪽에 문자열 보다 큰 있는지 확인 합니다.|  
|[CStringT::operator \<\=](../Topic/CStringT::operator%20%3C=.md)|연산자의 왼쪽에 문자열 보다 작거나 문자열 오른쪽에 있는지 확인 합니다.|  
|[CStringT::operator \>\=](../Topic/CStringT::operator%20%3E=.md)|문자열 연산자는 왼쪽에서 오른쪽에 있는 문자열 보다 크거나 있는지 확인 합니다.|  
  
## 설명  
 `CStringT`상속  [CSimpleStringT 클래스](../../atl-mfc-shared/reference/csimplestringt-class.md).  문자 조작, 정렬, 검색 등의 고급 기능을 구현 하면 `CStringT`.  
  
> [!NOTE]
>  `CStringT`개체의 예외를 throw 할 수 있습니다.  이런 경우는 `CStringT` 개체가 어떤 이유로 메모리에서 실행 합니다.  
  
 A `CStringT` 개체는 가변 길이 문자 시퀀스로 구성 됩니다.  `CStringT`Basic 유사한 구문을 사용 하 여 연산자와 함수를 제공 합니다.  연결 하 고 단순화 된 메모리 관리와 함께 비교 연산자 `CStringT` 개체 일반 문자 배열 보다 사용 하기 쉽게 합니다.  
  
> [!NOTE]
>  만들 수 있지만 `CStringT` 인스턴스가 포함 된 null 문자 포함에 대해 권장 합니다.  호출 메서드 및 연산자에서 `CStringT` 포함 된 null 문자를 포함 하는 개체는 의도 하지 않은 결과 생성할 수 있습니다.  
  
 다양 한 조합을 사용 하는 `BaseType` 및 `StringTraits` 매개 변수를 `CStringT` 수는 다음 형식에 들어온이 된 미리 ATL 라이브러리에서 개체.  
  
 ATL 응용 프로그램에서 사용 하는 경우:  
  
 `CString` `CStringA`, 및 `CStringW` \(MFC90. MFC DLL에서 내보낸DLL\) 사용자 Dll에서 되지 않습니다.  이 방지 하기 위한 것 `CStringT` 에서 정의 되 고 여러 번.  
  
> [!NOTE]
>  내보낼 때 링커 오류가 발생 하는 경우는 `CString`\-MFC 확장 DLL에서 Visual C\+\+.net 2002에서에서 클래스를 파생 하 고 대안을 적용 한 Visual C\+\+.net 2003에서는이 해결 되었으므로 "연결 오류 때 사용자 가져오기 CString\-Derived 클래스" \(Q309801\) 기술 자료 문서에서 설명한 문제 해결 코드를 제거 해야 합니다.  기술 자료 문서는 MSDN Library CD\-ROM이나 [http:\/\/support.microsoft.com\/default.aspx](http://support.microsoft.com/default.aspx)에 있습니다.  
  
 MFC 기반 응용 프로그램 내에서 사용할 수 있는 다음 문자열 형식은 다음과 같습니다.  
  
|CStringT 형식|선언|  
|-----------------|--------|  
|`CStringA`|ANSI 문자를 지 원하는 CRT 문자열을 입력 합니다.|  
|`CStringW`|유니코드 문자를 지 원하는 CRT 문자열을 입력 합니다.|  
|`CString`|ANSI와 유니코드 문자 형식 CRT 지원 합니다.|  
  
 다음 문자열 형식에 사용할 수 있는 프로젝트 위치  **ATL\_CSTRING\_NO\_CRT** 정의:  
  
|CStringT 형식|선언|  
|-----------------|--------|  
|**CAtlStringA**|ANSI 문자는 CRT 지원 하지 않는 문자열을 입력 합니다.|  
|**CAtlStringW**|유니코드 문자 지원 CRT 문자열을 입력 합니다.|  
|**CAtlString**|CRT 지원 하지 않는 ANSI와 유니코드 문자 형식|  
  
 다음 문자열 형식에 사용할 수 있는 프로젝트 위치  **ATL\_CSTRING\_NO\_CRT** 정의 되지 않았습니다.  
  
|CStringT 형식|선언|  
|-----------------|--------|  
|**CAtlStringA**|ANSI 문자를 지 원하는 CRT 문자열을 입력 합니다.|  
|**CAtlStringW**|유니코드 문자를 지 원하는 CRT 문자열을 입력 합니다.|  
|**CAtlString**|ANSI와 유니코드 문자 형식 CRT 지원 합니다.|  
  
 `CString`개체는 다음과 같은 특징이 있습니다.  
  
-   `CStringT`개체 연결 작업의 결과로 증가할 수 있습니다.  
  
-   `CStringT`개체에 따라 "값 의미 합니다." 생각은 `CStringT` 개체는 실제 문자열로, 문자열에 대 한 포인터는 아닌.  
  
-   자유롭게 사용할 수 있습니다 `CStringT` 개체에 대 한 `PCXSTR` 인수를 작동 합니다.  
  
-   문자열 버퍼에 대 한 사용자 지정 메모리 관리입니다.  자세한 내용은  [메모리 관리 및 CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
## CStringT 형식은 미리 정의 된.  
 때문에 `CStringT` 템플릿 인수를 사용 하 여 문자 형식을 정의 \(두  [wchar\_t](../../c-runtime-library/standard-types.md) 또는  [char](../../c-runtime-library/standard-types.md)\) 지원 되는 메서드 매개 변수 형식이 때때로 복잡할 수 있습니다.  이 문제를 단순화 하기 위해 미리 정의 된 형식 집합을 정의 되 고 전체에서 사용 되는 `CStringT` 클래스입니다.  다음 표에서 다양 한 형식을 보여 줍니다.  
  
|Name|설명|  
|----------|--------|  
|`XCHAR`|단일 문자 \(두 `wchar_t` 또는 `char`\)와 같은 문자 형식으로는 `CStringT` 개체.|  
|**YCHAR**|단일 문자 \(두 `wchar_t` 또는 `char`\) 반대 문자 형식으로 `CStringT` 개체입니다.|  
|`PXSTR`|문자열에 대 한 포인터 \(두 `wchar_t` 또는 `char`\)와 같은 문자 형식으로는 `CStringT` 개체.|  
|**PYSTR**|문자열에 대 한 포인터 \(두 `wchar_t` 또는 `char`\) 반대 문자 형식으로 `CStringT` 개체입니다.|  
|`PCXSTR`|에 대 한 포인터는  **const** 문자열 \(두 `wchar_t` 또는 `char`\) 같은 문자 형식으로 `CStringT` 개체.|  
|**PCYSTR**|에 대 한 포인터는  **const** 문자열 \(두 `wchar_t` 또는 `char`\) 반대 문자 형식으로 `CStringT` 개체.|  
  
> [!NOTE]
>  이전에 문서화 되지 않은 메서드를 사용 하는 코드 `CString` \(예:  **AssignCopy**\) 다음의 문서화 된 메서드를 사용 하 여 코드를 교체 해야 `CStringT` \(같은 `GetBuffer` 또는 `ReleaseBuffer`\).  이 메서드를 상속 `CSimpleStringT`.  
  
## 상속 계층 구조  
 [CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md)  
  
 `CStringT`  
  
## 요구 사항  
  
|Header|용도|  
|------------|--------|  
|cstringt.h|MFC 전용 문자열 개체|  
|atlstr.h|비 MFC string 개체입니다.|  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [ATL\/MFC Shared Classes](../../atl-mfc-shared/atl-mfc-shared-classes.md)   
 [CSimpleStringT Class](../../atl-mfc-shared/reference/csimplestringt-class.md)