---
title: "ISupportErrorInfoImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::ISupportErrorInfoImpl<piid>"
  - "ATL::ISupportErrorInfoImpl"
  - "ISupportErrorInfoImpl"
  - "ATL.ISupportErrorInfoImpl<piid>"
  - "ATL.ISupportErrorInfoImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "error information, ATL"
  - "ISupportErrorInfo ATL implementation"
  - "ISupportErrorInfoImpl class"
ms.assetid: e33a4b11-a123-41cf-bcea-7b19743902af
caps.latest.revision: 23
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ISupportErrorInfoImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스의 기본 구현을 제공 된 [ISupportErrorInfo Interface](http://msdn.microsoft.com/ko-kr/42d33066-36b4-4a5b-aa5d-46682e560f32) 및 단일 인터페이스만 개체에서 오류를 생성할 때 사용할 수 있습니다.  
  
> [!IMPORTANT]
>  이 클래스와 해당 멤버를 실행 하는 응용 프로그램에서 사용할 수 있는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## 구문  
  
```  
  
      template<  
const IID* piid   
>  
class ATL_NO_VTABLE ISupportErrorInfoImpl :  
public ISupportErrorInfo  
```  
  
#### 매개 변수  
 `piid`  
 지원 되는 인터페이스의 IID에 대 한 포인터  [IErrorInfo](http://msdn.microsoft.com/ko-kr/4dda6909-2d9a-4727-ae0c-b5f90dcfa447).  
  
## Members  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[ISupportErrorInfoImpl::InterfaceSupportsErrorInfo](../Topic/ISupportErrorInfoImpl::InterfaceSupportsErrorInfo.md)|인터페이스 식별 하는지 여부를 나타내는 `riid` 지원의  [IErrorInfo](http://msdn.microsoft.com/ko-kr/4dda6909-2d9a-4727-ae0c-b5f90dcfa447) 인터페이스.|  
  
## 설명  
 [ISupportErrorInfo Interface](http://msdn.microsoft.com/ko-kr/42d33066-36b4-4a5b-aa5d-46682e560f32) 오류 정보가 클라이언트에 반환 될 수 있습니다.  개체를 사용 하는  **IErrorInfo** 를 구현 해야  **ISupportErrorInfo**.  
  
 클래스 `ISupportErrorInfoImpl` 의 기본 구현을 제공 합니다.  **ISupportErrorInfo** 및 단일 인터페이스만 개체에서 오류를 생성할 때 사용할 수 있습니다.  예를 들면 다음과 같습니다.  
  
 [!code-cpp[NVC_ATL_COM#48](../../atl/codesnippet/CPP/isupporterrorinfoimpl-class_1.h)]  
  
## 상속 계층 구조  
 `ISupportErrorInfo`  
  
 `ISupportErrorInfoImpl`  
  
## 요구 사항  
 **헤더:**  atlcom.h  
  
## 참고 항목  
 [Class Overview](../../atl/atl-class-overview.md)