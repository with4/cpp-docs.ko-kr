---
title: "_U_STRINGorID Class | Microsoft Docs"
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
  - "ATL._U_STRINGorID"
  - "ATL::_U_STRINGorID"
  - "_U_STRINGorID"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_U_STRINGorID class"
  - "U_STRINGorID class"
ms.assetid: 443cdc00-d265-4b27-8ef3-2feb95f3e5e3
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _U_STRINGorID Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 인수 어댑터 클래스 두 리소스 이름이 있습니다 \(`LPCTSTR`s\) 또는 리소스 Id \(**UINT**s\) 호출자 ID를 사용 하 여 문자열에 변환할 필요 없이 함수에 전달 하는  **MAKEINTRESOURCE** 매크로.  
  
> [!IMPORTANT]
>  런타임에서 Windows를 실행 하는 응용 프로그램에서이 클래스와 해당 멤버를 사용할 수 없습니다.  
  
## 구문  
  
```  
  
class _U_STRINGorID  
  
```  
  
## Members  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|[\_U\_STRINGorID::\_U\_STRINGorID](../Topic/_U_STRINGorID::_U_STRINGorID.md)|생성자입니다.|  
  
### 공용 데이터 멤버  
  
|이름|설명|  
|--------|--------|  
|[\_U\_STRINGorID::m\_lpstr](../Topic/_U_STRINGorID::m_lpstr.md)|리소스 식별자입니다.|  
  
## 설명  
 이 클래스와 같은 Windows 리소스 관리 API 래퍼를 구현 하기 위한 설계는  [FindResource](http://msdn.microsoft.com/library/windows/desktop/ms648042),  [LoadIcon](http://msdn.microsoft.com/library/windows/desktop/ms648072), 및  [LoadMenu](http://msdn.microsoft.com/library/windows/desktop/ms647990) 허용 하는 함수는 `LPCTSTR` 인수는 리소스의 이름이 나 ID가 될 수 있습니다  
  
 두 개의 생성자 오버 로드에 정의 된 클래스: 허용 하나는 `LPCTSTR` 인수와 다른 허용는  **UINT** 인수.  **UINT** 인수를 변환 Windows 리소스 관리 함수를 사용 하 여 호환 되는 리소스 종류를  **MAKEINTRESOURCE** 매크로 및 클래스의 데이터 멤버에 저장 된 결과  [m\_lpstr](../Topic/_U_STRINGorID::m_lpstr.md).  인수에는 `LPCTSTR` 생성자는 변환 하지 않고 직접 저장 됩니다.  
  
## 요구 사항  
 **헤더:**  atlwin.h  
  
## 참고 항목  
 [Class Overview](../../atl/atl-class-overview.md)