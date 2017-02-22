---
title: "ComPtrRefBase 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "client/Microsoft::WRL::Details::ComPtrRefBase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ComPtrRefBase 클래스"
ms.assetid: 6d344c1a-cc13-4a3f-8a0d-f167ccb9348f
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# ComPtrRefBase 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## 구문  
  
```  
template <  
   typename T  
>  
class ComPtrRefBase;  
```  
  
#### 매개 변수  
 `T`  
 [ComPtr\<T\>](../windows/comptr-class.md) 형식은 ComPtr로 표시된 인터페이스뿐만 아니라 여기에서 파생된 형식입니다.  
  
## 설명  
 [ComPtrRef](../windows/comptrref-class.md) 클래스에 대한 기본 클래스를 나타냅니다.  
  
## 멤버  
  
### 공용 Typedefs  
  
|Name|설명|  
|----------|--------|  
|`InterfaceType`|템플릿 매개변수 `T`의 형식에 대한 동의어|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[ComPtrRefBase::operator IInspectable\*\* 연산자](../windows/comptrrefbase-operator-iinspectable-star-star-operator.md)|현재 [ptr\_](../windows/comptrrefbase-ptr-data-member.md) 데이터 멤버는 포인터에 \-포인터\-IInspectable 인터페이스를 캐스팅합니다.|  
|[ComPtrRefBase::operator IUnknown\*\* 연산자](../windows/comptrrefbase-operator-iunknown-star-star-operator.md)|현재 [ptr\_](../windows/comptrrefbase-ptr-data-member.md) 데이터 멤버는 포인터에 \-포인터\-IUnknown 인터페이스를 캐스팅합니다.|  
  
### 보호된 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[ComPtrRefBase::ptr\_ 데이터 멤버](../windows/comptrrefbase-ptr-data-member.md)|현재 템플릿 매개 변수로 지정된 형식에대한 포인터입니다.|  
  
## 상속 계층  
 `ComPtrRefBase`  
  
## 요구 사항  
 **헤더:** client.h  
  
 **네임스페이스**Microsoft::WRL::Details  
  
## 참고 항목  
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)