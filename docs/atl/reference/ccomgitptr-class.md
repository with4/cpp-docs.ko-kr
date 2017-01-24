---
title: "CComGITPtr Class | Microsoft Docs"
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
  - "ATL::CComGITPtr<T>"
  - "CComGITPtr"
  - "ATL.CComGITPtr"
  - "ATL.CComGITPtr<T>"
  - "ATL::CComGITPtr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComGITPtr class"
ms.assetid: af895acb-525a-4555-bb67-b241b7df515b
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComGITPtr Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 전역 인터페이스 테이블 \(GIT\) 및 인터페이스 포인터를 처리 하기 위한 메서드를 제공합니다.  
  
## 구문  
  
```  
  
      template <  
   class T   
>  
class CComGITPtr  
```  
  
#### 매개 변수  
 `T`  
 인터페이스 포인터를 GIT에 저장 유형을 지정 합니다.  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CComGITPtr::CComGITPtr](../Topic/CComGITPtr::CComGITPtr.md)|생성자입니다.|  
|[CComGITPtr::~CComGITPtr](../Topic/CComGITPtr::~CComGITPtr.md)|소멸자|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CComGITPtr::Attach](../Topic/CComGITPtr::Attach.md)|전역 인터페이스 테이블 \(GIT\)의 인터페이스 포인터를 등록 하려면이 메서드를 호출 합니다.|  
|[CComGITPtr::CopyTo](../Topic/CComGITPtr::CopyTo.md)|인터페이스는 전역 인터페이스 테이블 \(GIT\)에서 전달 된 포인터를 복사 하려면이 메서드를 호출 합니다.|  
|[CComGITPtr::Detach](../Topic/CComGITPtr::Detach.md)|인터페이스에서 연결을 해제 하려면이 메서드를 호출 하 여 `CComGITPtr` 개체입니다.|  
|[CComGITPtr::GetCookie](../Topic/CComGITPtr::GetCookie.md)|쿠키를 반환 하려면이 메서드를 호출 하는 `CComGITPtr` 개체입니다.|  
|[CComGITPtr::Revoke](../Topic/CComGITPtr::Revoke.md)|전역 인터페이스 테이블 \(GIT\)에서 인터페이스를 제거 하려면이 메서드를 호출 합니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CComGITPtr::operator DWORD](../Topic/CComGITPtr::operator%20DWORD.md)|쿠키에서 반환 된 `CComGITPtr` 개체입니다.|  
|[CComGITPtr::operator \=](../Topic/CComGITPtr::operator%20=.md)|할당 연산자입니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CComGITPtr::m\_dwCookie](../Topic/CComGITPtr::m_dwCookie.md)|쿠키입니다.|  
  
## 설명  
 자유 스레드된 마샬러를 집계 하 고 다른 개체에서 얻은 인터페이스 포인터를 사용 해야 하는 개체 인터페이스를 올바르게 마샬링되도록 추가 단계를 수행 해야 합니다.  일반적으로이 인터페이스 포인터를 GIT에 저장 하 고 사용 될 때마다 GIT에서 포인터를 얻는 합니다.  클래스 `CComGITPtr` 인터페이스 포인터를 GIT에 저장을 사용할 수 있도록 제공 됩니다.  
  
> [!NOTE]
>  글로벌 인터페이스 테이블 기능에만 Windows 95에 DCOM 버전 1.1 및 이후, Windows 98, Windows NT 4.0 서비스 팩 3 및 나중에 및 Windows 2000에서 사용할 수 있습니다.  
  
## 요구 사항  
 **헤더:** atlbase.h  
  
## 참고 항목  
 [자유 스레드된 마샬러](../../atl/atl-and-the-free-threaded-marshaler.md)   
 [Accessing Interfaces Across Apartments](http://msdn.microsoft.com/library/windows/desktop/ms682353)   
 [When to Use the Global Interface Table](http://msdn.microsoft.com/library/windows/desktop/ms693729)   
 [Class Overview](../../atl/atl-class-overview.md)