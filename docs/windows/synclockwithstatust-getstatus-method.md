---
title: "SyncLockWithStatusT::GetStatus 메서드 | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::GetStatus"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetStatus 메서드"
ms.assetid: d448b51d-a63d-40d9-a9ee-4aad3204118d
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# SyncLockWithStatusT::GetStatus 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```  
DWORD GetStatus() const;  
```  
  
## <a name="return-value"></a>반환 값  
 예: SyncLockWithStatusT 클래스에 기반 하는 개체에서 대기 작업의 결과 [뮤텍스](../windows/mutex-class1.md) 또는 [세마포](../windows/semaphore-class.md)합니다. 영 (0); 신호를 받은 상태를 반환 하는 대기 작업을 나타냅니다. 그렇지 않으면 경과 된 시간 제한 값과 같은 다른 상태가 발생 합니다.  
  
## <a name="remarks"></a>설명  
 현재 SyncLockWithStatusT 개체의 대기 상태를 검색합니다.  
  
 Getstatus () 함수 내부 값을 검색 [status_](../windows/synclockwithstatust-status-data-member.md) 데이터 멤버입니다. SyncLockWithStatusT 클래스를 기반으로 개체 잠금 작업을 수행할 때 개체는 먼저 사용할 수 있게 하는 개체에 대 한 대기 합니다. 이 대기 작업의 결과에 저장 되는 `status_` 데이터 멤버입니다. 가능한 값은 `status_` 데이터 멤버는 대기 작업의 반환 값입니다. 자세한 내용은의 반환 값을 참조 하십시오.는 **WaitForSingleObjectEx()** MSDN 라이브러리의 함수입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **네임 스페이스:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>참고 항목  
 [SyncLockWithStatusT 클래스](../windows/synclockwithstatust-class.md)