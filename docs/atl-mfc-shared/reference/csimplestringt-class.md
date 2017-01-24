---
title: "CSimpleStringT Class | Microsoft Docs"
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
  - "ATL.CSimpleStringT"
  - "ATL::CSimpleStringT"
  - "ATL::CSimpleStringT<BaseType>"
  - "ATL.CSimpleStringT<BaseType>"
  - "CSimpleStringT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSimpleStringT class"
  - "shared classes, CSimpleStringT"
  - "문자열[C++], ATL 클래스"
ms.assetid: 15814fcb-5b8f-4425-a97e-3b61fc9b48d8
caps.latest.revision: 19
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSimpleStringT Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스를 나타내는 한 `CSimpleStringT` 개체입니다.  
  
## 구문  
  
```  
  
      template <typename   
      BaseType  
      >  
class CSimpleStringT  
```  
  
#### 매개 변수  
 `BaseType`  
 문자 형식 문자열 클래스입니다.  다음 중 하나일 수 있습니다.  
  
-   `char`\(ANSI 문자열에 대 한\).  
  
-   `wchar_t`\(유니코드 문자열에 대 한\).  
  
-   **TCHAR** \(ANSI와 유니코드 문자열\)에 대 한.  
  
## Members  
  
### 공용 Typedefs  
  
|이름|설명|  
|--------|--------|  
|[CSimpleStringT::PCXSTR](../Topic/CSimpleStringT::PCXSTR.md)|상수 문자열에 대 한 포인터입니다.|  
|[CSimpleStringT::PXSTR](../Topic/CSimpleStringT::PXSTR.md)|문자열에 대 한 포인터입니다.|  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|[CSimpleStringT::CSimpleStringT](../Topic/CSimpleStringT::CSimpleStringT.md)|생성 `CSimpleStringT` 개체에서 다양 한 방법으로.|  
|[CSimpleStringT::~CSimpleStringT](../Topic/CSimpleStringT::~CSimpleStringT.md)|소멸자.|  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CSimpleStringT::Append](../Topic/CSimpleStringT::Append.md)|추가 된 `CSimpleStringT` 기존 개체 `CSimpleStringT` 개체입니다.|  
|[CSimpleStringT::AppendChar](../Topic/CSimpleStringT::AppendChar.md)|기존에 문자를 추가 `CSimpleStringT` 개체입니다.|  
|[CSimpleStringT::CopyChars](../Topic/CSimpleStringT::CopyChars.md)|문자를 다른 문자열에 복사합니다.|  
|[CSimpleStringT::CopyCharsOverlapped](../Topic/CSimpleStringT::CopyCharsOverlapped.md)|하나 이상의 문자에 버퍼를 겹치는 다른 문자열에 복사 합니다.|  
|[CSimpleStringT::Empty](../Topic/CSimpleStringT::Empty.md)|문자열의 길이는 0이 됩니다.|  
|[CSimpleStringT::FreeExtra](../Topic/CSimpleStringT::FreeExtra.md)|문자열 개체에서 이전에 할당 된 추가 메모리를 해제 합니다.|  
|[CSimpleStringT::GetAllocLength](../Topic/CSimpleStringT::GetAllocLength.md)|할당 된 길이 검색에 `CSimpleStringT` 개체입니다.|  
|[CSimpleStringT::GetAt](../Topic/CSimpleStringT::GetAt.md)|지정 된 위치의 문자를 반환합니다.|  
|[CSimpleStringT::GetBuffer](../Topic/CSimpleStringT::GetBuffer.md)|포인터를 반환 하는 자는 `CSimpleStringT`.|  
|[CSimpleStringT::GetBufferSetLength](../Topic/CSimpleStringT::GetBufferSetLength.md)|문자에 대 한 포인터를 반환 된 `CSimpleStringT`, 잘라내기가 지정한 길이.|  
|[CSimpleStringT::GetLength](../Topic/CSimpleStringT::GetLength.md)|문자 수가 반환 된 `CSimpleStringT` 개체.|  
|[CSimpleStringT::GetManager](../Topic/CSimpleStringT::GetManager.md)|메모리 관리자의 검색은 `CSimpleStringT` 개체입니다.|  
|[CSimpleStringT::GetString](../Topic/CSimpleStringT::GetString.md)|문자열 검색|  
|[CSimpleStringT::IsEmpty](../Topic/CSimpleStringT::IsEmpty.md)|테스트 여부는 `CSimpleStringT` 개체 문자가 포함 되어 있습니다.|  
|[CSimpleStringT::LockBuffer](../Topic/CSimpleStringT::LockBuffer.md)|참조 횟수를 사용 하지 않도록 설정 하 고 문자열 버퍼에서를 보호 합니다.|  
|[CSimpleStringT::Preallocate](../Topic/CSimpleStringT::Preallocate.md)|문자 버퍼에 대 한 특정 양의 메모리를 할당합니다.|  
|[CSimpleStringT::ReleaseBuffer](../Topic/CSimpleStringT::ReleaseBuffer.md)|컨트롤에 의해 반환 된 버퍼를 해제 `GetBuffer`.|  
|[CSimpleStringT::ReleaseBufferSetLength](../Topic/CSimpleStringT::ReleaseBufferSetLength.md)|컨트롤에 의해 반환 된 버퍼를 해제 `GetBuffer`.|  
|[CSimpleStringT::SetAt](../Topic/CSimpleStringT::SetAt.md)|지정 된 위치에 문자를 설정합니다.|  
|[CSimpleStringT::SetManager](../Topic/CSimpleStringT::SetManager.md)|메모리 관리자를 설정 하는 `CSimpleStringT` 개체입니다.|  
|[CSimpleStringT::SetString](../Topic/CSimpleStringT::SetString.md)|문자열을 설정 하는 `CSimpleStringT` 개체입니다.|  
|[CSimpleStringT::StringLength](../Topic/CSimpleStringT::StringLength.md)|지정 된 문자열에서 문자를 반환합니다.|  
|[CSimpleStringT::Truncate](../Topic/CSimpleStringT::Truncate.md)|지정 하는 문자열을 자릅니다.|  
|[CSimpleStringT::UnlockBuffer](../Topic/CSimpleStringT::UnlockBuffer.md)|참조 횟수를 사용 하 고 문자열 버퍼에서를 해제 합니다.|  
  
### Public 연산자  
  
|이름|설명|  
|--------|--------|  
|[CSimpleStringT::operator PCXSTR](../Topic/CSimpleStringT::operator%20PCXSTR.md)|저장 된 문자를 직접 액세스 하는 `CSimpleStringT` 개체를 C 스타일 문자열로.|  
|[CSimpleStringT::operator](../Topic/CSimpleStringT::operator.md)|지정 된 위치의 문자를 반환 합니다.\-운영자 대체 `GetAt`.|  
|[CSimpleStringT::operator \+\=](../Topic/CSimpleStringT::operator%20+=.md)|기존 문자열의 끝에 새 문자열을 연결합니다.|  
|[CSimpleStringT::operator \=](../Topic/CSimpleStringT::operator%20=.md)|새 값에 지정 된 `CSimpleStringT` 개체.|  
  
## 설명  
 `CSimpleStringT`Visual C\+\+에서 지원 되는 다양 한 문자열 클래스는 기본 클래스가입니다.  이 메모리 관리 기본 버퍼 조작 및 문자열 개체에 대 한 최소한의 지원을 제공합니다.  고급 문자열 개체를 참조 하십시오.  [CStringT 클래스](../../atl-mfc-shared/reference/cstringt-class.md).  
  
## 요구 사항  
 **헤더:** atlsimpstr.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [ATL\/MFC Shared Classes](../../atl-mfc-shared/atl-mfc-shared-classes.md)