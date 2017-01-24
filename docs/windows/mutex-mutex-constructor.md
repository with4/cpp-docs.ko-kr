---
title: "Mutex::Mutex 생성자 | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::Mutex::Mutex"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Mutex, 생성자"
ms.assetid: 504afcdc-775a-4c98-a06f-4fb4663eba3f
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Mutex::Mutex 생성자
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Mutex 클래스의 새 인스턴스를 초기화합니다.  
  
## <a name="syntax"></a>구문  
  
```  
explicit Mutex(  
   HANDLE h  
);  
  
Mutex(  
   _Inout_ Mutex&& h  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `h`  
 핸들, 핸들에 대한 rvalue 참조, Mutex 개체에 대한 rvalue 참조입니다.  
  
## <a name="remarks"></a>설명  
 첫 번째 생성자는 지정된 핸들에서 Mutex 개체를 초기화합니다. 두 번째 생성자는 지정된 핸들에서 Mutex 개체를 초기화한 다음 뮤텍스의 소유권을 현재 Mutex 개체로 옮깁니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **네임 스페이스:** Microsoft::WRL::Wrappers
 
 ## <a name="see-also"></a>참고 항목
 [Mutex 클래스](../windows/mutex-class1.md)