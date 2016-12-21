---
title: "CRegKey Class | Microsoft Docs"
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
  - "CRegKey"
  - "ATL::CRegKey"
  - "ATL.CRegKey"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL, 레지스트리"
  - "CRegKey class"
  - "레지스트리, 키 삭제"
  - "레지스트리, 값 삭제"
  - "레지스트리, 쓰기"
ms.assetid: 3afce82b-ba2c-4c1a-8404-dc969e1af74b
caps.latest.revision: 25
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRegKey Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스 항목에서 시스템 레지스트리를 조작 하기 위한 메서드를 제공 합니다.  
  
> [!IMPORTANT]
>  런타임에서 Windows를 실행 하는 응용 프로그램에서이 클래스와 해당 멤버를 사용할 수 없습니다.  
  
## 구문  
  
```  
  
class CRegKey  
  
```  
  
## Members  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|[CRegKey::CRegKey](../Topic/CRegKey::CRegKey.md)|생성자입니다.|  
|[CRegKey::~CRegKey](../Topic/CRegKey::~CRegKey.md)|소멸자|  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CRegKey::Attach](../Topic/CRegKey::Attach.md)|첨부는 HKEY에이 메서드를 호출 하는 `CRegKey` 설정 하 여 개체의  [m\_hKey](../Topic/CRegKey::m_hKey.md) 구성원 핸들을 `hKey`.|  
|[CRegKey::Close](../Topic/CRegKey::Close.md)|해제 하려면이 메서드를 호출 하 여  [m\_hKey](../Topic/CRegKey::m_hKey.md) 멤버를 처리 하 고 NULL로 설정 합니다.|  
|[CRegKey::Create](../Topic/CRegKey::Create.md)|하위 키의 이름으로 존재 하지 않는 경우 지정 된 키를 만들려면이 메서드를 호출 합니다. `hKeyParent`.|  
|[CRegKey::DeleteSubKey](../Topic/CRegKey::DeleteSubKey.md)|지정 된 키를 레지스트리에서 제거 하려면이 메서드를 호출 합니다.|  
|[CRegKey::DeleteValue](../Topic/CRegKey::DeleteValue.md)|값 필드를 제거 하려면이 메서드를 호출 합니다.  [m\_hKey](../Topic/CRegKey::m_hKey.md).|  
|[CRegKey::Detach](../Topic/CRegKey::Detach.md)|분리 하는이 메서드를 호출 하는  [m\_hKey](../Topic/CRegKey::m_hKey.md) 핸들 멤버는 `CRegKey` 개체 및 설정 `m_hKey` NULL로.|  
|[CRegKey::EnumKey](../Topic/CRegKey::EnumKey.md)|열린 레지스트리 키의 하위 키 열거 하려면이 메서드를 호출 합니다.|  
|[CRegKey::Flush](../Topic/CRegKey::Flush.md)|열린 레지스트리 키의 특성을 모두 레지스트리에 쓸이 메서드를 호출 합니다.|  
|[CRegKey::GetKeySecurity](../Topic/CRegKey::GetKeySecurity.md)|열기 레지스트리 키를 보호 하는 보안 설명자의 복사본을 검색 하려면이 메서드를 호출 합니다.|  
|[CRegKey::NotifyChangeKeyValue](../Topic/CRegKey::NotifyChangeKeyValue.md)|이 메서드는 특성 또는 열린 레지스트리 키의 내용을 변경 하는 방법에 대 한 호출자에 게를 알립니다.|  
|[CRegKey::Open](../Topic/CRegKey::Open.md)|지정 된 키를 열고 설정 하려면이 메서드를 호출 합니다.  [m\_hKey](../Topic/CRegKey::m_hKey.md) 이 키의 핸들입니다.|  
|[CRegKey::QueryBinaryValue](../Topic/CRegKey::QueryBinaryValue.md)|값을 지정 된 이름에 대 한 이진 데이터를 검색 하려면이 메서드를 호출 합니다.|  
|[CRegKey::QueryDWORDValue](../Topic/CRegKey::QueryDWORDValue.md)|DWORD 값을 지정 된 이름에 대 한 데이터를 검색 하려면이 메서드를 호출 합니다.|  
|[CRegKey::QueryGUIDValue](../Topic/CRegKey::QueryGUIDValue.md)|GUID 값을 지정 된 이름에 대 한 데이터를 검색 하려면이 메서드를 호출 합니다.|  
|[CRegKey::QueryMultiStringValue](../Topic/CRegKey::QueryMultiStringValue.md)|Multistring 값을 지정 된 이름에 대 한 데이터를 검색 하려면이 메서드를 호출 합니다.|  
|[CRegKey::QueryQWORDValue](../Topic/CRegKey::QueryQWORDValue.md)|QWORD 값을 지정 된 이름에 대 한 데이터를 검색 하려면이 메서드를 호출 합니다.|  
|[CRegKey::QueryStringValue](../Topic/CRegKey::QueryStringValue.md)|문자열 값을 지정 된 이름에 대 한 데이터를 검색 하려면이 메서드를 호출 합니다.|  
|[CRegKey::QueryValue](../Topic/CRegKey::QueryValue.md)|지정한 값 필드의 데이터를 검색 하려면이 메서드를 호출 합니다.  [m\_hKey](../Topic/CRegKey::m_hKey.md).  이전 버전의이 메서드가 더 이상 지원 되지 및로 표시 된  **ATL\_DEPRECATED**.|  
|[CRegKey::RecurseDeleteKey](../Topic/CRegKey::RecurseDeleteKey.md)|지정 된 키를 레지스트리에서 제거 하 고 모든 하위 키를 명시적으로 제거 하려면이 메서드를 호출 합니다.|  
|[CRegKey::SetBinaryValue](../Topic/CRegKey::SetBinaryValue.md)|레지스트리 키의 이진 값을 설정 하려면이 메서드를 호출 합니다.|  
|[CRegKey::SetDWORDValue](../Topic/CRegKey::SetDWORDValue.md)|레지스트리 키의 DWORD 값을 설정 하려면이 메서드를 호출 합니다.|  
|[CRegKey::SetGUIDValue](../Topic/CRegKey::SetGUIDValue.md)|레지스트리 키의 GUID 값을 설정 하려면이 메서드를 호출 합니다.|  
|[CRegKey::SetKeySecurity](../Topic/CRegKey::SetKeySecurity.md)|레지스트리 키의 보안을 설정 하려면이 메서드를 호출 합니다.|  
|[CRegKey::SetKeyValue](../Topic/CRegKey::SetKeyValue.md)|지정 된 키 값을 지정 된 필드에 데이터를 저장 하려면이 메서드를 호출 합니다.|  
|[CRegKey::SetMultiStringValue](../Topic/CRegKey::SetMultiStringValue.md)|Multistring 값을 레지스트리 키를 설정 하려면이 메서드를 호출 합니다.|  
|[CRegKey::SetQWORDValue](../Topic/CRegKey::SetQWORDValue.md)|QWORD 레지스트리 키의 값을 설정 하려면이 메서드를 호출 합니다.|  
|[CRegKey::SetStringValue](../Topic/CRegKey::SetStringValue.md)|레지스트리 키의 문자열 값을 설정 하려면이 메서드를 호출 합니다.|  
|[CRegKey::SetValue](../Topic/CRegKey::SetValue.md)|지정한 값 필드에 데이터를 저장 하려면이 메서드를 호출 합니다.  [m\_hKey](../Topic/CRegKey::m_hKey.md).  이전 버전의이 메서드가 더 이상 지원 되지 및로 표시 된  **ATL\_DEPRECATED**.|  
  
### Public 연산자  
  
|이름|설명|  
|--------|--------|  
|[CRegKey::operator HKEY](../Topic/CRegKey::operator%20HKEY.md)|변환 된 `CRegKey` 는 HKEY 개체.|  
|[CRegKey::operator \=](../Topic/CRegKey::operator%20=.md)|할당 연산자입니다.|  
  
### 공용 데이터 멤버  
  
|이름|설명|  
|--------|--------|  
|[CRegKey::m\_hKey](../Topic/CRegKey::m_hKey.md)|와 관련 된 레지스트리 키에 대 한 핸들이 포함 된 `CRegKey` 개체.|  
|[CRegKey::m\_pTM](../Topic/CRegKey::m_pTM.md)|포인터를 `CAtlTransactionManager` 개체|  
  
## 설명  
 `CRegKey`만들고 키 및 시스템 레지스트리 값을 삭제 하기 위한 메서드를 제공 합니다.  레지스트리 소프트웨어 버전 번호, 설치 된 하드웨어 및 COM 개체의 논리적 물리적 매핑 시스템 구성 요소에 대 한 정의 특정 설치 설정이 되어 있습니다.  
  
 `CRegKey`지정 된 컴퓨터에는 시스템 레지스트리 프로그래밍 인터페이스를 제공합니다.  예를 들어, 특정 레지스트리 키를 열 수 호출 `CRegKey::Open`.  검색 하거나 데이터 값을 수정 하려면 호출 `CRegKey::QueryValue` 또는 `CRegKey::SetValue`, 각각.  호출 키를 닫으려면 `CRegKey::Close`.  
  
 키를 닫을 때 해당 레지스트리 데이터 \(플러시 했습니다\) 하드 디스크에 기록 됩니다.  이 프로세스는 몇 초가 걸릴 수 있습니다.  하드 디스크에 응용 프로그램 레지스트리 데이터를 명시적으로 작성 해야 하는 경우 호출할 수 있는  [RegFlushKey](http://msdn.microsoft.com/library/windows/desktop/ms724867) Win32 함수.  그러나  **RegFlushKey** 많은 시스템 리소스를 사용 하 고 꼭 필요할 때만 호출 해야 합니다.  
  
> [!IMPORTANT]
>  레지스트리 위치를 지정할 수 있도록 하는 메서드는 신뢰할 수 없는 데이터를 읽을 수가 있습니다.  사용 하는 방법  [RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911) 이 함수는 NULL 종료 문자열을 명시적으로 처리 하지 않는 고려해 야 합니다.  두 조건에 대 한 호출 코드에서 확인 하 여  
  
## 요구 사항  
 **헤더:**  atlbase.h  
  
## 참고 항목  
 [DCOM 샘플](../../top/visual-cpp-samples.md)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [Registry Overview](http://msdn.microsoft.com/library/windows/desktop/ms724871)   
 [Registry Functions](http://msdn.microsoft.com/library/windows/desktop/ms724875)   
 [Registry Value Types](http://msdn.microsoft.com/library/windows/desktop/ms724884)