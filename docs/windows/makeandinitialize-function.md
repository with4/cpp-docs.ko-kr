---
title: "MakeAndInitialize 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Details::MakeAndInitialize"
dev_langs: 
  - "C++"
ms.assetid: 71ceeb12-d2a2-4317-b010-3dcde1b39467
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# MakeAndInitialize 함수
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

지정된 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] 클래스를 초기화합니다.  이 함수는 동일한 모듈에서 정의된 구성요소를 설명하는 데 사용됩니다.  
  
## 구문  
  
```cpp  
template <typename T, typename I,   
typename TArg1,   
typename TArg2,   
typename TArg3,   
typename TArg4,   
typename TArg5,   
typename TArg6,   
typename TArg7,   
typename TArg8,   
typename TArg9> HRESULT MakeAndInitialize(_Outptr_result_nullonfailure_ I** ppvObject, TArg1 &&arg1, TArg2 &&arg2, TArg3 &&arg3, TArg4 &&arg4, TArg5 &&arg5, TArg6 &&arg6, TArg7 &&arg7, TArg8 &&arg8, TArg9 &&arg9) throw()  
  
```  
  
#### 매개 변수  
 `T`  
 사용자 지정 클래스에서 상속 되는 `WRL::RuntimeClass`.  
  
 `TArg1`  
 지정된 런타임 클래스를 전달하는 인수 1의 형식.  
  
 `TArg2`  
 지정된 런타임 클래스를 전달하는 인수 2의 형식.  
  
 `TArg3`  
 지정된 런타임 클래스를 전달하는 인수 3의 형식  
  
 `TArg4`  
 지정된 런타임 클래스를 전달하는 인수 4의 형식.  
  
 `TArg5`  
 지정된 런타임 클래스를 전달하는 인수 5의 형식.  
  
 `TArg6`  
 지정된 런타임 클래스를 전달하는 인수 6의 형식.  
  
 `TArg7`  
 지정된 런타임 클래스를 전달하는 인수 7의 형식.  
  
 `TArg8`  
 지정된 런타임 클래스를 전달하는 인수 8의 형식.  
  
 `TArg9`  
 지정된 런타임 클래스를 전달하는 인수 9의 형식.  
  
 `arg1`  
 지정된 런타임 클래스를 전달하는 인수 1.  
  
 `arg2`  
 지정된 런타임 클래스를 전달하는 인수 2.  
  
 `arg3`  
 지정된 런타임 클래스를 전달하는 인수 3.  
  
 `arg4`  
 지정된 런타임 클래스를 전달하는 인수 4.  
  
 `arg5`  
 지정된 런타임 클래스를 전달하는 인수 5.  
  
 `arg6`  
 지정된 런타임 클래스를 전달하는 인수 6.  
  
 `arg7`  
 지정된 런타임 클래스를 전달하는 인수 7.  
  
 `arg8`  
 지정된 런타임 클래스를 전달하는 인수 8.  
  
 `arg9`  
 지정된 런타임 클래스를 전달하는 인수 9.  
  
## 반환 값  
 `HRESULT` 값입니다.  
  
## 설명  
 이 함수와 [Microsoft::WRL::Make](../windows/make-function.md) 사이의 차이점과 예제에 대해 더 많이 알고 싶다면, [방법: 직접 WRL 구성 요소 인스턴스화](../windows/how-to-instantiate-wrl-components-directly.md) 를 참조하십시오.  
  
## 요구 사항  
 **헤더:** implements.h  
  
 **네임스페이스**Microsoft::WRL::Details  
  
## 참고 항목  
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)