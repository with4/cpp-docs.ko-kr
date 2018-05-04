---
title: COM 소개 | Microsoft Docs
ms.custom: index-page
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- COM
ms.assetid: 120735d9-db71-4ad3-a730-ce576ea2354e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 938d0c45cae5ec9a2988f77f539af1a3d5513b83
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="introduction-to-com"></a>COM 소개
COM 켜져 있습니다 "개체 모델" 기본 어떤 ActiveX 컨트롤 및 OLE 작성 됩니다. COM 응용 프로그램을 호스트 하 고 다른 구성 요소에 해당 기능을 노출 하는 개체 수 있습니다. 개체 표시 방식을 프로세스 간에 및 네트워크를 통해 이러한 인터페이스의 작동 방식 모두를 정의 합니다. 또한 COM 개체의 수명 주기를 정의합니다.  
  
 기본 COM에는 이러한 개념:  
  
-   [인터페이스](../atl/interfaces-atl.md) -개체를 통해 그 기능을 제공 하는 메커니즘입니다.  
  
-   [IUnknown](../atl/iunknown.md) — 다른 모든 기반으로 하는 기본 인터페이스입니다. 참조 횟수 및 쿼리 COM. 통해를 실행 하는 메커니즘 인터페이스 구현  
  
-   [참조 횟수](../atl/reference-counting.md) -있는 개체 (또는 엄격 하 게 인터페이스)를 결정 것은 더 이상 사용 되지 고 따라서 자유롭게 면 자체를 제거 하는 방법입니다.  
  
-   [QueryInterface](../atl/queryinterface.md) -지정 된 인터페이스에 대 한 개체를 쿼리 하는 데 사용 하는 메서드.  
  
-   [마샬링](../atl/marshaling.md) -개체를 통해 스레드, 프로세스 및 위치 독립성에 대 한 네트워크 경계에서 사용할 수 있도록 하는 메커니즘입니다.  
  
-   [집계](../atl/aggregation.md) -다른 하나의 개체만 만들 수 있는 방법을 사용 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [COM 및 ATL 소개](../atl/introduction-to-com-and-atl.md)   
 [구성 요소 개체 모델](http://msdn.microsoft.com/library/windows/desktop/ms694363)

