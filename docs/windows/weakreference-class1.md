---
title: "WeakReference 클래스 | Microsoft Docs"
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
  - "implements/Microsoft::WRL::Details::WeakReference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "WeakReference 클래스"
ms.assetid: 3f4c956b-dbbd-49b1-8cfa-9509a9956c97
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# WeakReference 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## 구문  
  
```  
class WeakReference;  
```  
  
## 설명  
 Windows 런타입 또는 클래식 COM을 사용하는 *약한 참조* 를 나타냅니다.  약한 참조에 액세스할 수 없는 개체를 나타냅니다.  
  
 `WeakReference` 개체는 개체에 대한 포인터인 *강한 참조* 및 Resolve\(\) 메서드에 의해 분배된 강한 참조의 복사 수인 *강한 참조 횟수* 를 유지합니다.   강한 참조 개수가 0이 아닌 동안 강력한 참조는 유효하고 개체를 액세스할 수 있습니다.  강력한 참조 횟수가 0이 되면 강력한 참조가 잘못 되었고 및 해당 개체를 액세스할 수 없습니다.  
  
 약한 참조 개체는 일반적으로 외부 스레드 또는 응용프로구램에 의해 제어되는 존재인 개체를 사용하곤 합니다.  예를 들어, 파일 개체에 대한 참조는 약한 참조 개체를 생성합니다.  파일이 열려 있을 때에 강력한 참조는 유효합니다.  하지만 파일이 닫혀있는 경우, 강한 참조는 잘못된 것입니다.  
  
 약한 참조 메서드는 안전 스레드 입니다.  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[WeakReference::WeakReference 생성자](../windows/weakreference-weakreference-constructor.md)|약한 참조 클래스의 새로운 인스터스를 초기화합니다.|  
|[WeakReference::~WeakReference 소멸자](../windows/weakreference-tilde-weakreference-destructor.md)|약한 참조 클래스의 현재 인스턴스를 초기화하지 않습니다.\(소멸시킵니다.\)|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[WeakReference::DecrementStrongReference 메서드](../windows/weakreference-decrementstrongreference-method.md)|현재 약한 참조 개체의 강한 참조 수를 감소시킵니다.|  
|[WeakReference::IncrementStrongReference 메서드](../windows/weakreference-incrementstrongreference-method.md)|현재 약한 참조 개체의 강한 참조 수를 증가시킵니다.|  
|[WeakReference::Resolve 메서드](../windows/weakreference-resolve-method.md)|강한 참조 횟수가 0이 아니면 고정 참조가 현재 값으로 지정된 된 포인터를 설정 합니다.|  
|[WeakReference::SetUnknown 메서드](../windows/weakreference-setunknown-method.md)|지정한 인터페이스 포인터를 현재 약한 참조 개체에 대한 강한 참조를 설정합니다.|  
  
## 상속 계층  
 `WeakReference`  
  
## 요구 사항  
 **헤더:** implements.h  
  
 **네임스페이스**Microsoft::WRL::Details  
  
## 참고 항목  
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)