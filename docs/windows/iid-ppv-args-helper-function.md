---
title: "IID_PPV_ARGS_Helper 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "client/IID_PPV_ARGS_Helper"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IID_PPV_ARGS_Helper 함수"
ms.assetid: afee9b23-8df1-4575-903f-e9ba748418f0
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# IID_PPV_ARGS_Helper 함수
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

확인된 지정된 인수의 형식에서 파생하는 `IUnknown` 인터페이스입니다.  
  
> [!IMPORTANT]
>  이 템플릿 특수화는 WRL 인프라구조체를 지원하고 직접적으로 코드를 사용하는 것을 의도합니다.  [IID\_PPV\_ARGS](http://msdn.microsoft.com/library/windows/desktop/ee330727.aspx) 대신에 사용합니다.  
  
## 구문  
  
```  
template<  
   typename T  
>  
void** IID_PPV_ARGS_Helper(  
   _Inout_ Microsoft::WRL::Details::ComPtrRef<T> pp  
);  
```  
  
#### 매개 변수  
 `T`  
 인수 `pp` 형식입니다.  
  
 `pp`  
 이중 간접 포인터입니다.  
  
## 반환 값  
 인수 `pp` 는 포인터\-포인터 `void` 로 캐스팅합니다.  
  
## 설명  
 컴파일 타임 오류가 발생합니다. 이는 템플릿 매개 변수 `T` 가 `IUnknown` 로 도출되지 않을 경우 입니다.  
  
## 요구 사항  
 **헤더:** client.h  
  
## 참고 항목  
 [Reference \(Windows Runtime Library\)](http://msdn.microsoft.com/ko-kr/00000000-0000-0000-0000-000000000000)