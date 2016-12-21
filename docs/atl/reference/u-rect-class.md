---
title: "_U_RECT Class | Microsoft Docs"
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
  - "ATL::_U_RECT"
  - "_U_RECT"
  - "ATL._U_RECT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_U_RECT class"
  - "U_RECT class"
ms.assetid: 5f880a2d-09cf-4327-bf32-a3519c4dcd63
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _U_RECT Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 인수 어댑터 클래스가 `RECT` 포인터 또는 참조 포인터를 측면에서 구현 되는 함수에 전달 됩니다.  
  
> [!IMPORTANT]
>  런타임에서 Windows를 실행 하는 응용 프로그램에서이 클래스와 해당 멤버를 사용할 수 없습니다.  
  
## 구문  
  
```  
  
class _U_RECT  
  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[\_U\_RECT::\_U\_RECT](../Topic/_U_RECT::_U_RECT.md)|생성자입니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[\_U\_RECT::m\_lpRect](../Topic/_U_RECT::m_lpRect.md)|포인터는 `RECT`.|  
  
## 설명  
 두 개의 생성자 오버 로드에 정의 된 클래스: 허용 하나는  **RECT &** 인수와 다른 허용는 `LPRECT` 인수.  첫 번째 생성자 참조 인수의 주소 클래스의 단일 데이터 멤버에 저장  [m\_lpRect](../Topic/_U_RECT::m_lpRect.md).  포인터 생성자 인수를 변환 하지 않고 직접 저장 됩니다.  
  
## 요구 사항  
 **헤더:**  atlwin.h  
  
## 참고 항목  
 [Class Overview](../../atl/atl-class-overview.md)