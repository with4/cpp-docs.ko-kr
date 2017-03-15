---
title: "ComPtrRef 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "client/Microsoft::WRL::Details::ComPtrRef"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ComPtrRef 클래스"
ms.assetid: d6bdfd20-e977-45b4-9ac1-1b8efbdb77de
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# ComPtrRef 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL 인프라구조체를 지원하고 코드에서 직접적으로 사용되는 것을 의도하지 않습니다.  
  
## 구문  
  
```  
template <  
   typename T  
>  
class ComPtrRef : public ComPtrRefBase<T>;  
```  
  
#### 매개 변수  
 `T`  
 [ComPtr\<T\>](../windows/comptr-class.md) 형식은 ComPtr로 표시된 인터페이스뿐만 아니라 여기에서 파생된 형식입니다.  
  
## 설명  
 ComPtr 형식의 개체에 대 한 참조를 나타내는\<T\>.  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[ComPtrRef::ComPtrRef 생성자](../windows/comptrref-comptrref-constructor.md)|다른 ComPtrRef 개체에 지정된 된 포인터를 ComPtrRef 클래스의 새 인스턴스를 초기화합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[ComPtrRef::GetAddressOf 메서드](../windows/comptrref-getaddressof-method.md)|현재 ComPtrRef 개체로 표시되는 인터페이스에 대한 포인터의 주소를 검색합니다.|  
|[ComPtrRef::ReleaseAndGetAddressOf 메서드](../windows/comptrref-releaseandgetaddressof-method.md)|현재 ComPtrRef 개체를 삭제하고 ComPtrRef 개체로 표시되는 인터페이스 포인터\-에\-a\-포인터를 반환합니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[ComPtrRef::operator InterfaceType\*\* 연산자](../windows/comptrref-operator-interfacetype-star-star-operator.md)|현재 ComPtrRef 개체를 삭제하고 ComPtrRef 개체로 표시되는 인터페이스 포인터\-에\-a\-포인터를 반환합니다.|  
|[ComPtrRef::operator T\* 연산자](../windows/comptrref-operator-t-star-operator.md)|현재 ComPtrRef 개체의 [ptr\_](../windows/comptrrefbase-ptr-data-member.md) 데이터 멤버의 값을 반환합니다.|  
|[ComPtrRef::operator void\*\* 연산자](../windows/comptrref-operator-void-star-star-operator.md)|현재 ComPtrRef 개체, `void` 포인터\-포인터\- ComPtrRef 개체에 의해 표시된 인터페이스에 대한 포인터 캐스팅을 삭제합니다, 그리고 캐스트 포인터를 반환 합니다.|  
|[ComPtrRef::operator\* 연산자](../windows/comptrref-operator-star-operator.md)|현재 ComPtrRef 개체를 나타내는 인터페이스 포인터를 검색합니다.|  
|[ComPtrRef::operator\=\= 연산자](../windows/comptrref-operator-equality-operator.md)|ComPtrRef 개체가 같지 않은지 여부를 나타냅니다.|  
|[ComPtrRef::operator\!\= 연산자](../windows/comptrref-operator-inequality-operator.md)|두 ComPtrRef 개체가 같지 않은지 여부를 나타냅니다.|  
  
## 상속 계층  
 `ComPtrRefBase`  
  
 `ComPtrRef`  
  
## 요구 사항  
 **헤더:** client.h  
  
 **네임스페이스:** Microsoft::WRL::Details  
  
## 참고 항목  
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)