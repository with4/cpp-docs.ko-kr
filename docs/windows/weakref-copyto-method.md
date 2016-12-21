---
title: "WeakRef::CopyTo 메서드 | Microsoft Docs"
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
  - "client/Microsoft::WRL::WeakRef::CopyTo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CopyTo 메서드"
ms.assetid: f83de6da-b3d4-41a6-9845-cd725ecf3b75
caps.latest.revision: 5
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# WeakRef::CopyTo 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

사용 가능한 경우 지정된 포인터 변수에 인터페이스에 대한 포인터를 할당합니다.  
  
## 구문  
  
```  
HRESULT CopyTo(  
   REFIID riid,  
   _Deref_out_ IInspectable** ptr  
);  
  
template<  
   typename U  
>  
HRESULT CopyTo(  
   _Deref_out_ U** ptr  
);  
  
HRESULT CopyTo(  
   _Deref_out_ IWeakReference** ptr  
);  
```  
  
#### 매개 변수  
 `U`  
 IInspectable 인터페이스의 포인터입니다.`U`가 IInspectable에서 파생되지 않으면 오류가 발생합니다.  
  
 `riid`  
 인터페이스 ID입니다.`riid`가 **IWeakReference**에서 파생되지 않으면 오류가 발생합니다.  
  
 `ptr`  
 IInspectable 또는 IWeakReference의 이중 간접 포인터입니다.  
  
## 반환 값  
 성공하면 S\_OK이고, 그렇지 않으면 실패를 설명하는 HRESULT가 발생합니다. 자세한 내용은 설명 부분을 참조하세요.  
  
## 설명  
 반환 값 S\_OK는 이 작업이 성공했음을 의미하지만 약한 참조가 강한 참조로 확인되었는지를 나타내지 않습니다. S\_OK가 반환되면 `p` 매개 변수가 강한 참조인지 테스트합니다. 즉, `p` 매개 변수가 `nullptr`과 같지 않은지 테스트합니다.  
  
 Windows 10 SDK부터는 약한 참조를 가져올 수 없는 경우 이 메서드에서 WeakRef 인스턴스를 `nullptr`로 설정하지 않으므로 `nullptr`에 대해 WeakRef를 검사하는 오류 검사 코드를 사용하지 않아야 합니다. 대신 메서드가 성공했는지 확인하려면 반환된 HRESULT를 검사하거나 `nullptr`에서 `ptr`를 검사합니다.  
  
## 요구 사항  
 **헤더:** client.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [WeakRef 클래스](../windows/weakref-class.md)