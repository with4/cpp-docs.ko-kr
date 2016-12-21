---
title: "_U_MENUorID Class | Microsoft Docs"
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
  - "ATL._U_MENUorID"
  - "ATL::_U_MENUorID"
  - "_U_MENUorID"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_U_MENUorID class"
  - "U_MENUorID class"
ms.assetid: cfc8032b-61b4-4a68-ba3a-92b82500ccae
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _U_MENUorID Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스 래퍼를 제공  **CreateWindow** 및  **즉, 개발자**.  
  
> [!IMPORTANT]
>  런타임에서 Windows를 실행 하는 응용 프로그램에서이 클래스와 해당 멤버를 사용할 수 없습니다.  
  
## 구문  
  
```  
  
class _U_MENUorID  
  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[\_U\_MENUorID::\_U\_MENUorID](../Topic/_U_MENUorID::_U_MENUorID.md)|생성자입니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[\_U\_MENUorID::m\_hMenu](../Topic/_U_MENUorID::m_hMenu.md)|메뉴에 대 한 핸들입니다.|  
  
## 설명  
 이 인수 어댑터 클래스 두 id가 있습니다 \(**UINT**s\) 또는 메뉴 핸들 \(`HMENU`s\) 호출자의 부품에는 명시적 캐스트가 필요 없이 함수에 전달 될 합니다.  
  
 이 클래스 래퍼는 Windows api를 구현 하기 위한 설계는 특히  [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) 및  [즉, 개발자](http://msdn.microsoft.com/library/windows/desktop/ms632680) 기능을 모두 허용는 `HMENU` 자식 창 식별자가 될 수 있는 인수 \(**UINT**\) 메뉴 핸들 대신.  이 클래스를 사용 하려면 매개 변수로 볼 수 있습니다 예를 들어,  [CWindowImpl::Create](../Topic/CWindowImpl::Create.md).  
  
 두 개의 생성자 오버 로드에 정의 된 클래스: 허용 하나는  **UINT** 인수와 다른 허용는 `HMENU` 인수.  **UINT** 인수에 캐스팅 된 바로 `HMENU` 생성자 클래스의 데이터 멤버에 저장 된 결과에서  [m\_hMenu](../Topic/_U_MENUorID::m_hMenu.md).  인수에는 `HMENU` 생성자는 변환 하지 않고 직접 저장 됩니다.  
  
## 요구 사항  
 **헤더:**  atlwin.h  
  
## 참고 항목  
 [Class Overview](../../atl/atl-class-overview.md)