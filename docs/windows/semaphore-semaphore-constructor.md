---
title: "Semaphore::Semaphore 생성자 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::Semaphore::Semaphore"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Semaphore, 생성자"
ms.assetid: 91c22ae7-181e-460d-ad40-70c3a53b26fd
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Semaphore::Semaphore 생성자
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Semaphore 클래스의 새 인스턴스를 초기화합니다.  
  
## <a name="syntax"></a>구문  
  
```  
explicit Semaphore(  
   HANDLE h  
);  
  
WRL_NOTHROW Semaphore(  
   _Inout_ Semaphore&& h  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `h`  
 Semaphore 개체에 대한 핸들 또는 rvalue 참조입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **네임 스페이스:** Microsoft::WRL::Wrappers
 
 ## <a name="see-also"></a>참고 항목
 [Semaphore 클래스](../windows/semaphore-class.md)