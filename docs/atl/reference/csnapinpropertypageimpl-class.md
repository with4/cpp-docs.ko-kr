---
title: "CSnapInPropertyPageImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CSnapInPropertyPageImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSnapInPropertyPageImpl class"
  - "속성 페이지, ATL"
  - "snap-ins"
  - "snap-ins, 속성 페이지"
ms.assetid: 75bdce5a-985e-4166-bd44-493132e023c4
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CSnapInPropertyPageImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 스냅인 속성 페이지 개체를 구현 하는 방법을 제공 합니다.  
  
> [!IMPORTANT]
>  런타임에서 Windows를 실행 하는 응용 프로그램에서이 클래스와 해당 멤버를 사용할 수 없습니다.  
  
## 구문  
  
```  
  
CSnapInPropertyPageImpl : public CDialogImplBase  
  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CSnapInPropertyPageImpl::CSnapInPropertyPageImpl](../Topic/CSnapInPropertyPageImpl::CSnapInPropertyPageImpl.md)|생성자입니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CSnapInPropertyPageImpl::CancelToClose](../Topic/CSnapInPropertyPageImpl::CancelToClose.md)|변경의 상태는  **확인** 및  **취소** 단추.|  
|[CSnapInPropertyPageImpl::Create](../Topic/CSnapInPropertyPageImpl::Create.md)|새로 만든 초기화 `CSnapInPropertyPageImpl` 개체입니다.|  
|[CSnapInPropertyPageImpl::OnApply](../Topic/CSnapInPropertyPageImpl::OnApply.md)|클릭할 때 프레임 워크에 의해 호출 된  **지금 적용** 단추 마법사 형식의 속성 시트를 사용 하는 동안.|  
|[CSnapInPropertyPageImpl::OnHelp](../Topic/CSnapInPropertyPageImpl::OnHelp.md)|클릭할 때 프레임 워크에 의해 호출 된  **도움말** 단추 마법사 형식의 속성 시트를 사용 하는 동안.|  
|[CSnapInPropertyPageImpl::OnKillActive](../Topic/CSnapInPropertyPageImpl::OnKillActive.md)|현재 페이지를 더 이상 활성화 되어 있을 때 프레임 워크에 의해 호출 됩니다.|  
|[CSnapInPropertyPageImpl::OnQueryCancel](../Topic/CSnapInPropertyPageImpl::OnQueryCancel.md)|클릭할 때 프레임 워크에 의해 호출 된  **취소** 단추 및 취소 작업이 수행 되기 전에.|  
|[CSnapInPropertyPageImpl::OnReset](../Topic/CSnapInPropertyPageImpl::OnReset.md)|클릭할 때 프레임 워크에 의해 호출 된  **재설정** 단추 마법사 형식의 속성 시트를 사용 하는 동안.|  
|[CSnapInPropertyPageImpl::OnSetActive](../Topic/CSnapInPropertyPageImpl::OnSetActive.md)|현재 페이지의 활성화 될 때 프레임 워크에 의해 호출 됩니다.|  
|[CSnapInPropertyPageImpl::OnWizardBack](../Topic/CSnapInPropertyPageImpl::OnWizardBack.md)|클릭할 때 프레임 워크에 의해 호출 된**다시** 단추 마법사 형식의 속성 시트를 사용 하는 동안.|  
|[CSnapInPropertyPageImpl::OnWizardFinish](../Topic/CSnapInPropertyPageImpl::OnWizardFinish.md)|클릭할 때 프레임 워크에 의해 호출 된  **완료** 단추 마법사 형식의 속성 시트를 사용 하는 동안.|  
|[CSnapInPropertyPageImpl::OnWizardNext](../Topic/CSnapInPropertyPageImpl::OnWizardNext.md)|클릭할 때 프레임 워크에 의해 호출 된 `Next` 단추 마법사 형식의 속성 시트를 사용 하는 동안.|  
|[CSnapInPropertyPageImpl::QuerySiblings](../Topic/CSnapInPropertyPageImpl::QuerySiblings.md)|모든 페이지의 속성 시트에 있는 현재 메시지를 전달합니다.|  
|[CSnapInPropertyPageImpl::SetModified](../Topic/CSnapInPropertyPageImpl::SetModified.md)|호출을 활성화 하거나 비활성화할 수 있는  **지금 적용** 단추.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CSnapInPropertyPageImpl::m\_psp](../Topic/CSnapInPropertyPageImpl::m_psp.md)|Windows  **PROPSHEETPAGE** 구조를 사용 하는 `CSnapInPropertyPageImpl` 개체.|  
  
## 설명  
 `CSnapInPropertyPageImpl`스냅인 속성 페이지 개체의 기본 구현을 제공 합니다.  스냅인 속성 페이지의 기본 기능 몇 가지 다른 인터페이스를 통해 구현 및 형식에 매핑합니다.  
  
## 상속 계층 구조  
 `CDialogImplBase`  
  
 `CSnapInPropertyPageImpl`  
  
## 요구 사항  
 **헤더:**  atlsnap.h  
  
## 참고 항목  
 [Class Overview](../../atl/atl-class-overview.md)