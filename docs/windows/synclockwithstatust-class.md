---
title: "SyncLockWithStatusT 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SyncLockWithStatusT 클래스"
ms.assetid: 4832fd93-0ac8-4168-9404-b43fefea7476
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# SyncLockWithStatusT 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```  
template <  
   typename SyncTraits  
>  
class SyncLockWithStatusT : public SyncLockT<SyncTraits>;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `SyncTraits`  
 단독으로 사용할 수 있는 형식 또는 리소스의 소유권을 공유 합니다.  
  
## <a name="remarks"></a>설명  
 단독으로 사용할 수 있는 형식을 나타내는 리소스의 소유권을 공유 합니다.  
  
 SyncLockWithStatusT 클래스는 구현 하는 데 사용 되는 [뮤텍스](../windows/mutex-class1.md) 및 [세마포](../windows/semaphore-class.md) 클래스입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[Synclockwithstatust:: Synclockwithstatust 생성자](../windows/synclockwithstatust-synclockwithstatust-constructor.md)|SyncLockWithStatusT 클래스의 새 인스턴스를 초기화합니다.|  
  
### <a name="protected-constructors"></a>Protected 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[Synclockwithstatust:: Synclockwithstatust 생성자](../windows/synclockwithstatust-synclockwithstatust-constructor.md)|SyncLockWithStatusT 클래스의 새 인스턴스를 초기화합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[Synclockwithstatust:: Getstatus 메서드](../windows/synclockwithstatust-getstatus-method.md)|현재 SyncLockWithStatusT 개체의 대기 상태를 검색합니다.|  
|[Synclockwithstatust:: Islocked 메서드](../windows/synclockwithstatust-islocked-method.md)|현재 SyncLockWithStatusT 개체; 리소스를 소유 하는지 여부를 나타냅니다. SyncLockWithStatusT 개체 즉, *잠긴*합니다.|  
  
### <a name="protected-data-members"></a>보호된 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[Synclockwithstatust:: Status_ 데이터 멤버](../windows/synclockwithstatust-status-data-member.md)|현재 SyncLockWithStatusT 개체를 기반으로 개체의 기본 결과 잠금 작업 한 후 작업을 대기할 보류 합니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `SyncLockT`  
  
 `SyncLockWithStatusT`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **네임 스페이스:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL::Wrappers::Details 네임 스페이스](../windows/microsoft-wrl-wrappers-details-namespace.md)