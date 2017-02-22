---
title: "CAxWindow2T Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CAxWindow2T<TBase>"
  - "ATL::CAxWindow2T"
  - "CAxWindow2T"
  - "ATL.CAxWindow2T<TBase>"
  - "ATL.CAxWindow2T"
  - "CAxWindow2"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAxWindow2 class"
ms.assetid: b87bc943-7991-4537-b902-2138d7f4d837
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CAxWindow2T Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 ActiveX 컨트롤을 호스팅하고 라이센스가 있는 ActiveX 컨트롤을 호스팅하기 위한 지원 수도 있습니다 창을 조작 하기 위한 메서드를 제공 합니다.  
  
> [!IMPORTANT]
>  런타임에서 Windows를 실행 하는 응용 프로그램에서이 클래스와 해당 멤버를 사용할 수 없습니다.  
  
## 구문  
  
```  
  
      template <   
class TBase= CWindow   
>  
class CAxWindow2T :   
public CAxWindowT< TBase >  
```  
  
#### 매개 변수  
 *TBase*  
 클래스는 `CAxWindowT` 파생 됩니다.  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CAxWindow2T::CAxWindow2T](../Topic/CAxWindow2T::CAxWindow2T.md)|`CAxWindow2T` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CAxWindow2T::Create](../Topic/CAxWindow2T::Create.md)|호스트 창을 만듭니다.|  
|[CAxWindow2T::CreateControlLic](../Topic/CAxWindow2T::CreateControlLic.md)|ActiveX 사용이 허가 된 컨트롤 초기화를 만들고 호스팅하는 지정한 창에.|  
|[CAxWindow2T::CreateControlLicEx](../Topic/CAxWindow2T::CreateControlLicEx.md)|ActiveX 사용이 허가 된 컨트롤을 만들고 초기화, 지정 된 창에서 호스팅하 및 인터페이스 포인터 \(또는 포인터\)을 컨트롤에서 검색 합니다.|  
|[CAxWindow2T::GetWndClassName](../Topic/CAxWindow2T::GetWndClassName.md)|창 클래스의 이름을 검색 하는 정적 메서드.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CAxWindow2T::operator \=](../Topic/CAxWindow2T::operator%20=.md)|할당 된 `HWND` 기존 `CAxWindow2T` 개체입니다.|  
  
## 설명  
 `CAxWindow2T`해당 호스트 창을 조작 하는 메서드는 ActiveX 컨트롤을 제공 합니다.  `CAxWindow2T`라이센스가 있는 ActiveX 컨트롤을 호스팅하기 위한 지원 수도 있습니다.  호스팅에 의해 제공 됩니다 "**AtlAxWinLic80**"에 의해 래핑되는 `CAxWindow2T`.  
  
 클래스 `CAxWindow2` 의 특수화로 구현 되는 `CAxWindow2T` 클래스입니다.  이 특수화로 선언 됩니다.  
  
 `typedef CAxWindow2T <CWindow> CAxWindow2;`  
  
> [!NOTE]
>  `CAxWindowT`멤버에서 문서화 된  [CAxWindow](../../atl/reference/caxwindow-class.md).  
  
 참조  [사용할 수 있는 호스팅 ActiveX 컨트롤을 사용 하 여 ATL 클래스](../../atl/hosting-activex-controls-using-atl-axhost.md) 이 클래스의 멤버를 사용 하는 샘플에 대 한.  
  
## 상속 계층 구조  
 `TBase`  
  
 `CAxWindowT`  
  
 `CAxWindow2T`  
  
## 요구 사항  
 **헤더:**  atlwin.h  
  
## 참고 항목  
 [Class Overview](../../atl/atl-class-overview.md)   
 [컨트롤 포함 FAQ](../../atl/atl-control-containment-faq.md)