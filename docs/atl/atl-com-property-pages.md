---
title: "ATL COM 속성 페이지 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL COM 개체"
  - "ATL 속성 페이지"
  - "COM 개체, ATL"
  - "COM 속성 페이지"
  - "속성 페이지, ATL"
  - "속성 페이지, COM"
ms.assetid: 663c7caa-2e5e-4b5c-b8ea-fd434ceb1654
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# ATL COM 속성 페이지
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

COM 속성 페이지 속성을 설정 하는 사용자 인터페이스를 제공 \(또는 메서드 호출\)의 하나 이상의 COM 개체입니다.  속성 페이지 컨트롤 속성에 디자인 타임에 설정할 수 있는 풍부한 사용자 인터페이스를 제공 하는 ActiveX 컨트롤에 의해 광범위 하 게 사용 됩니다.  
  
 속성 페이지는 COM 개체는 구현에서  [IPropertyPage](http://msdn.microsoft.com/library/windows/desktop/ms691246) 또는  [IPropertyPage2](http://msdn.microsoft.com/library/windows/desktop/ms683996) 인터페이스.  이러한 인터페이스 연관 시킬 페이지를 사용할 수 있는 메서드를 제공 합니다.는 `site` \(페이지의 컨테이너를 나타내는 COM 개체\)와 여러 개의  *개체* \(COM 개체에 속성 페이지의 사용자가 변경한 내용에 대 한 응답 해당 메서드를 호출 합니다.\).  속성 페이지 컨테이너 속성 페이지 인터페이스를 사용자가 내부 개체를 표시 하거나 숨기려면, 사용자 인터페이스 및 변경 내용을 적용할 때 수행한 페이지 지를 알려줍니다 메서드를 호출에 대 한 책임이 있습니다.  
  
 각 속성 페이지 속성을 설정할 수 있습니다 개체와 독립적으로 완벽 하 게 구축할 수 있습니다.  모든 속성 페이지 요구 특정 인터페이스 \(또는 인터페이스\)을 이해 하 고 인터페이스에 메서드를 호출 하는 사용자 인터페이스를 제공할 수 있습니다.  
  
 자세한 내용은  [속성 시트 및 속성 페이지](http://msdn.microsoft.com/library/windows/desktop/ms686577) 에 있는 [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
## 단원 내용  
 [속성 페이지를 지정합니다.](../atl/specifying-property-pages.md)  
 사용자 컨트롤에 대 한 속성 페이지를 지정 하는 단계를 나열 하 고 예제 클래스를 보여 줍니다.  
  
 [속성 페이지 구현](../atl/implementing-property-pages.md)  
 재정의 하는 메서드를 포함 하 여 속성 페이지를 구현 하는 단계를 나열 합니다.  ATLPages 샘플 프로그램에 기반한 완전 한 예제를 통해 단계별로 설명 합니다.  
  
## 관련 단원  
 [ATLPages 샘플](../top/visual-cpp-samples.md)  
 ATLPages 샘플을 사용 하 여 속성 페이지를 구현 하는 샘플 요약 `IPropertyPageImpl`.  
  
 [ATL](../atl/active-template-library-atl-concepts.md)  
 액티브 템플릿 라이브러리를 사용 하 여 프로그래밍 하는 방법에 개념 항목에 대 한 링크를 제공 합니다.  
  
## 참고 항목  
 [개념](../atl/active-template-library-atl-concepts.md)