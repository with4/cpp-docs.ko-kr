---
title: ATL COM 속성 페이지 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- property pages, COM
- ATL COM objects
- COM property pages
- property pages, ATL
- COM objects, ATL
- ATL property pages
ms.assetid: 663c7caa-2e5e-4b5c-b8ea-fd434ceb1654
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d5d7904b9f31a1be858dadaa8a087c720c277465
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32357534"
---
# <a name="atl-com-property-pages"></a>ATL COM 속성 페이지
속성을 설정 하기 위한 사용자 인터페이스를 제공 하는 COM 속성 페이지 (또는 메서드를 호출할) 하나 이상의 COM 개체입니다. 속성 페이지 컨트롤 속성을 디자인 타임에 설정 될 수 있는 풍부한 사용자 인터페이스를 제공 하기 위해 ActiveX 컨트롤에서 광범위 하 게 사용 됩니다.  
  
 속성 페이지는 COM 구현 하는 개체는 [IPropertyPage](http://msdn.microsoft.com/library/windows/desktop/ms691246) 또는 [IPropertyPage2](http://msdn.microsoft.com/library/windows/desktop/ms683996) 인터페이스입니다. 페이지와 연결 될 수 있는 메서드를 제공 하는 이러한 인터페이스는 `site` (페이지의 컨테이너를 나타내는 COM 개체) 및 다양 한 *개체* 변경 사항에 따라 해당 메서드가 호출 됩니다 (COM 개체 사용자가 변경한 속성 페이지의). 속성 페이지 컨테이너는 페이지를 표시 하거나 숨기는 사용자 인터페이스를 지정 하 고 변경 내용을 적용 하는 경우 기본 개체에 사용자가 변경한 경우 속성 페이지 인터페이스에서 메서드를 호출 하는 일을 담당 합니다.  
  
 각 속성 페이지가 속성을 설정할 수 개체와는 별도로 빌드할 수 있습니다. 모든 작업을 속성 페이지를 특정 인터페이스 (또는 인터페이스 집합이)를 이해 하 고 해당 인터페이스의 메서드를 호출 하는 사용자 인터페이스를 제공 하는 데 필요한 것입니다.  
  
 자세한 내용은 참조 [속성 시트 및 속성 페이지](http://msdn.microsoft.com/library/windows/desktop/ms686577) 에 [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)]합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [속성 페이지 지정](../atl/specifying-property-pages.md)  
 제어에 대 한 속성 페이지를 지정 하는 단계를 나열 하 고 예제에서는 클래스를 보여 줍니다.  
  
 [속성 페이지 구현](../atl/implementing-property-pages.md)  
 속성 페이지를 재정의 하는 메서드를 포함 하 여 구현 하는 단계를 나열 합니다. ATLPages 샘플 프로그램을 기반으로 하는 전체 예제를 안내 합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [ATLPages 샘플](../visual-cpp-samples.md)  
 ATLPages 샘플을 사용 하 여 속성 페이지를 구현 하는 샘플 추상 `IPropertyPageImpl`합니다.  
  
 [ATL](../atl/active-template-library-atl-concepts.md)  
 액티브 템플릿 라이브러리를 사용하여 프로그래밍하는 방법에 대한 개념 항목의 링크를 제공합니다.  
  
## <a name="see-also"></a>참고 항목  
 [개념](../atl/active-template-library-atl-concepts.md)

