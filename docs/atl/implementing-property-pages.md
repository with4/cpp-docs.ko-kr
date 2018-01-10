---
title: "속성 페이지 구현 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- IPropertyPage2 class
- IPropertyPage class
- property pages, implementing
ms.assetid: 62f29440-33a7-40eb-a1ef-3634c95f640c
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ac80bdd9e38d14b53aea7b691d480272cce66e7b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="implementing-property-pages"></a>속성 페이지 구현
속성 페이지는 COM 구현 하는 개체는 `IPropertyPage` 또는 **IPropertyPage2** 인터페이스입니다. ATL 속성 페이지를 통해 구현에 대 한 지원을 제공는 [ATL 속성 페이지 마법사](../atl/reference/atl-property-page-wizard.md) 에 [클래스 추가 대화 상자](../ide/add-class-dialog-box.md)합니다.  
  
 ATL을 사용 하 여 속성 페이지를 만들려면:  
  
-   ATL 동적 연결 라이브러리 (DLL) 서버 프로젝트를 열거나 만듭니다.  
  
-   열기는 [클래스 추가 대화 상자](../ide/add-class-dialog-box.md) 선택 **ATL 속성 페이지**합니다.  
  
-   속성 페이지 (있어 사용자 인터페이스) 스레드 아파트로 인지 확인 합니다.  
  
-   제목, 설명 (문서 문자열) 및 페이지와 연결할 도움말 파일을 설정 합니다.  
  
-   속성 페이지의 사용자 인터페이스 역할을 하도록 생성 된 대화 상자 리소스에 컨트롤을 추가 합니다.  
  
-   유효성 검사를 수행, 페이지 사이트를 업데이트 또는 페이지와 연결 된 개체를 업데이트 하 여 페이지의 사용자 인터페이스의 변화에 따라 응답 합니다. 특히, [IPropertyPageImpl::SetDirty](../atl/reference/ipropertypageimpl-class.md#setdirty) 때 사용자 변경을 속성 페이지에 있습니다.  
  
-   필요에 따라 재정의 `IPropertyPageImpl` 아래의 지침을 사용 하 여 메서드.  
  
    |IPropertyPageImpl 메서드|재정의 하려는 경우...|노트|  
    |------------------------------|----------------------------------|-----------|  
    |[SetObjects](../atl/reference/ipropertypageimpl-class.md#setobjects)|지원 되는 인터페이스와 페이지에 전달 되는 개체의 수에 대 한 기본 온전성 검사를 수행 합니다.|기본 클래스 구현을 호출 하기 전에 사용자 고유의 코드를 실행 합니다. 설정 되 고 개체 예상과 따르지, 호출 가능한 한 빨리 실패 해야 있습니다.|  
    |[활성화](../atl/reference/ipropertypageimpl-class.md#activate)|페이지의 사용자 인터페이스 (예를 들어 개체에서 현재 속성 값을 사용 하 여 대화 상자 컨트롤을 설정, 컨트롤을 동적으로 만들 또는 다른 초기화 수행)을 초기화 합니다.|기본 클래스에 해당 키를 업데이트 하려고 하기 전에 대화 상자 창 및 모든 컨트롤을 만들 수 있도록 코드 하기 전에 기본 클래스 구현을 호출 합니다.|  
    |[적용](../atl/reference/ipropertypageimpl-class.md#apply)|속성 설정을 확인 하 고 개체를 업데이트 합니다.|수행 하지 않습니다 추적과 호출 이후 기본 클래스 구현을 호출 하지 않아도가 됩니다.|  
    |[비활성화](../atl/reference/ipropertypageimpl-class.md#deactivate)|창 관련 항목을 정리 합니다.|기본 클래스 구현을 속성 페이지를 나타내는 대화 상자를 삭제 합니다. 대화 상자를 제거 하기 전에 정리 해야 할 경우에 기본 클래스를 호출 하기 전에 코드를 추가 해야 합니다.|  
  
 예제 속성 페이지 구현에 대 한 참조 [예: 속성 페이지 구현](../atl/example-implementing-a-property-page.md)합니다.  
  
> [!NOTE]
>  속성 페이지에서 ActiveX 컨트롤을 호스트 하려는 경우 마법사에서 생성 된 클래스의 파생을 변경 해야 합니다. 대체 **CDialogImpl\<CYourClass >** 와 **CAxDialogImpl\<CYourClass >** 기본 클래스 목록에 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [속성 페이지](../atl/atl-com-property-pages.md)   
 [ATLPages 샘플](../visual-cpp-samples.md)

