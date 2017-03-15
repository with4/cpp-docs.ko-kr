---
title: "SimpleClassFactory::CreateInstance 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::SimpleClassFactory::CreateInstance"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CreateInstance 메서드"
ms.assetid: 17b7947a-2608-49d9-b730-fef76501c9bc
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# SimpleClassFactory::CreateInstance 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

지정된 인터페이스의 인스턴스를 만듭니다.  
  
## 구문  
  
```  
  
STDMETHOD(  
   CreateInstance  
)  
   (_Inout_opt_ IUnknown* pUnkOuter,   
   REFIID riid,   
   _Deref_out_ void** ppvObject);  
```  
  
#### 매개 변수  
 `pUnkOuter`  
 `nullptr` 로 존재합니다; 그렇지 않으면 반환 값은 CLASS\_E\_NOAGGREGATION입니다.  
  
 SimpleClassFactory는 집계를 지원 하지 않습니다.  집계 지원 하 고 생성되는 개체는 집합체의 일부일 경우, `pUnkOuter` 집계의 제어 IUnknown 인터페이스 포인터를 것입니다.  
  
 `riid`  
 인터페이스를 만드는 개체의 ID입니다.  
  
 `ppvObject`  
 이 작업이 완료되면, `riid` 클래스 템플릿 매개 변수에 의해 지정된 개체의 인스턴스에 대한 포인터입니다.  
  
## 반환 값  
 성공 하면 S\_OK 그렇지 않으면 오류를 나타내는 HRESULT입니다.  
  
## 설명  
 클래스 템플릿 매개 변수에 지정된 기본 클래스에서 파생되지 않은 경우, 어설션 오류가 발생하며 \_\_WRL\_STRICT\_\_를 정의하는 경우 [RuntimeClass](../windows/runtimeclass-class.md) 는 도출되지 않거나, 또는 WinRt WinRtClassicComMix [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) 열거형 값을 사용하여 구성되지 않습니다.  
  
## 요구 사항  
 **헤더:** module.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [SimpleClassFactory 클래스](../windows/simpleclassfactory-class.md)