---
title: "Implementing Property Pages | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IPropertyPage class"
  - "IPropertyPage2 class"
  - "속성 페이지, 구현"
ms.assetid: 62f29440-33a7-40eb-a1ef-3634c95f640c
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Implementing Property Pages
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

속성 페이지는 COM 개체는 구현에서 `IPropertyPage` 또는  **IPropertyPage2** 인터페이스.  ATL 속성 페이지를 구현 하기 위한 지원을 제공 된  [ATL 속성 페이지 마법사](../atl/reference/atl-property-page-wizard.md) 에  [클래스 추가 대화 상자](../ide/add-class-dialog-box.md).  
  
 ATL을 사용 하 여 속성 페이지를 만들려면  
  
-   ATL 동적 연결 라이브러리 \(DLL\) 서버 프로젝트를 열거나 만듭니다.  
  
-   열려 있는  [클래스 추가 대화 상자](../ide/add-class-dialog-box.md) 선택 하 고  **ATL 속성 페이지**.  
  
-   속성 페이지 \(이 사용자 인터페이스가 있으므로\) 스레드 아파트 인지 확인 합니다.  
  
-   제목, 설명 \(문서 문자열\) 및 해당 페이지와 관련 된 도움말 파일을 설정 합니다.  
  
-   속성 페이지의 사용자 인터페이스로 작동 하는 생성 된 대화 상자 리소스에 컨트롤을 추가 합니다.  
  
-   페이지의 사용자 인터페이스를 사용 하 여 유효성 검사를 수행 하거나 페이지 사이트 업데이트 페이지와 관련 된 개체를 업데이트 하려면 변경에 응답 합니다.  특히,  [IPropertyPageImpl::SetDirty](../Topic/IPropertyPageImpl::SetDirty.md) 때 사용자가 변경 하는 속성 페이지.  
  
-   필요에 따라 재정의 `IPropertyPageImpl` 아래 지침을 사용 하는 방법.  
  
    |IPropertyPageImpl 메서드|원하는 경우 다시 정의...|참고|  
    |---------------------------|---------------------|--------|  
    |[SetObjects](../Topic/IPropertyPageImpl::SetObjects.md)|페이지 및 지 원하는 인터페이스에 전달 되는 개체 수가 기본 온전성 검사를 수행 합니다.|기본 클래스 구현을 호출 하기 전에 자신의 코드를 실행 합니다.  설정 하 고 개체를 기대에 맞지 않는 경우 최대한 빨리 호출을 실패 합니다.|  
    |[활성화](../Topic/IPropertyPageImpl::Activate.md)|\(대화 컨트롤 속성 값이 현재 개체를 설정 하는 예를 들어, 컨트롤을 동적으로 생성 합니다\) 페이지의 사용자 인터페이스를 초기화 합니다.|기본 클래스 업데이트 전에 대화 창과 모든 컨트롤을 만들 수 있도록 코드에 앞서 기본 클래스 구현을 호출 합니다.|  
    |[적용](../Topic/IPropertyPageImpl::Apply.md)|속성 설정을 확인 하 고 개체를 업데이트 합니다.|호출 추적과 수행 하지 않으므로 기본 클래스 구현을 호출 하지 않아도가 됩니다.|  
    |[비활성화](../Topic/IPropertyPageImpl::Deactivate.md)|창 관련 된 항목을 정리 합니다.|기본 클래스 구현은 속성 페이지를 나타내는 대화 상자를 소멸 시킵니다.  대화 상자가 삭제 되기 전에 정리 해야 하는 경우 기본 클래스를 호출 하기 전에 코드를 추가 해야 합니다.|  
  
 예제 속성 페이지 구현을 참조 하십시오.  [예제: 속성 페이지 구현](../atl/example-implementing-a-property-page.md).  
  
> [!NOTE]
>  호스트 ActiveX 컨트롤에 속성 페이지를 원하는 경우 마법사에서 생성 된 클래스의 파생을 변경 해야 합니다.  대체  **CDialogImpl \<CYourClass\>** 와  **CAxDialogImpl \<CYourClass\>** 의 기본 클래스 목록에서.  
  
## 참고 항목  
 [속성 페이지](../atl/atl-com-property-pages.md)   
 [ATLPages 샘플](../top/visual-cpp-samples.md)