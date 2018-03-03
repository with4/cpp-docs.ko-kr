---
title: "OLE 백그라운드: MFC 구현 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IMarshall
- IMoniker
dev_langs:
- C++
helpviewer_keywords:
- MFC libraries, implementing
- OLE MFC library implementation
- OLE IMarshal interface
- IMoniker interface, MFC
- IMarshall class [MFC]
- OLE, compound files
- OLE IMoniker interface
- OLE IUnknown
ms.assetid: 2b67016a-d78e-4d60-925f-c28ec8fb6180
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 530cc14135fd38e2177e00dc87974e96ffe24b6c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="ole-background-mfc-implementation"></a>OLE 백그라운드: MFC 구현
원시 OLE API의 크기와 복잡성으로 인해 OLE 응용 프로그램을 직접 작성하기 위해 호출하는 데 시간이 오래 걸릴 수 있습니다. OLE의 MFC 라이브러리 구현의 목표는 완벽한 기능을 갖춘 OLE 지원 응용 프로그램을 작성하기 위해 해야 할 작업의 양을 줄이는 것입니다.  
  
 이 문서에서는 MFC 내부에서 구현되지 않은 OLE API 부분을 설명합니다. 토론에는 구현 된 사항이 매핑되는 방식을 Windows SDK의 OLE 섹션에 설명 합니다.  
  
##  <a name="_core_portions_of_ole_not_implemented_by_the_class_library"></a>클래스 라이브러리에서 구현 되지 않은 ole 부분  
 OLE의 몇 가지 인터페이스와 기능은 MFC에서 직접 지원하지 않습니다. 이러한 기능을 사용하는 경우 OLE API를 직접 호출할 수 있습니다.  
  
 IMoniker 인터페이스  
 `IMoniker` 인터페이스는 클래스 라이브러리에서 구현됩니다(예: `COleServerItem` 클래스). 그러나 이전에 프로그래머에게 노출되지 않았습니다. 이 인터페이스에 대 한 자세한 내용은 Windows SDK의 OLE 단원에서 OLE 모니커 구현을 참조 합니다. 그러나 클래스도 참조 [CMonikerFile](../mfc/reference/cmonikerfile-class.md) 및 [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md)합니다.  
  
 IUnknown 및 IMarshal 인터페이스  
 **IUnknown** 인터페이스는 클래스 라이브러리에서 구현 되지만 프로그래머에 게 노출 되지 않습니다. **IMarshal** 인터페이스는 클래스 라이브러리에서 구현 되지 않지만 내부적으로 사용 됩니다. 클래스 라이브러리를 사용하여 빌드된 자동화 서버는 이미 마샬링 기능이 내장되어 있습니다.  
  
 Docfiles(복합 파일)  
 복합 파일은 클래스 라이브러리에서 부분적으로 지원됩니다. 만드는 것 이상으로 직접 복합 파일을 조작하는 함수는 지원하지 않습니다. MFC 클래스를 사용 하 여 **COleFileStream** 표준 파일 함수와 스트림 조작을 지원 하도록 합니다. 자세한 내용은 문서 참조 [컨테이너: 복합 파일](../mfc/containers-compound-files.md)합니다.  
  
 In-process 서버와 개체 처리기  
 In-process 서버와 개체 처리기를 통해 시각적 데이터 편집을 구현하거나 DLL(동적 연결 라이브러리)의 모든 COM(구성 요소 개체 모델) 개체를 구현할 수 있습니다. 이렇게 하려면 OLE API를 직접 호출하여 DLL을 구현할 수 있습니다. 그러나 사용자 인터페이스가 없는 자동화 서버를 작성하는 경우에는 AppWizard를 사용하여 해당 서버를 In-process 서버로 만든 다음 DLL에 완전히 포함시킬 수 있습니다. 이러한 항목에 대 한 자세한 내용은 참조 [자동화 서버](../mfc/automation-servers.md)합니다.  
  
> [!TIP]
>  자동화 서버를 구현하는 가장 쉬운 방법은 DLL에 배치하는 것입니다. MFC는 이 방법을 지원합니다.  
  
 Microsoft Foundation OLE 클래스가 OLE 인터페이스를 구현 하는 방법에 대 한 자세한 내용은 MFC 기술 참고 사항 참조 [38](../mfc/tn038-mfc-ole-iunknown-implementation.md), [39](../mfc/tn039-mfc-ole-automation-implementation.md), 및 [40](../mfc/tn040-mfc-ole-in-place-resizing-and-zooming.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [OLE 백그라운드](../mfc/ole-background.md)   
 [OLE 백그라운드 구현 전략](../mfc/ole-background-implementation-strategies.md)

