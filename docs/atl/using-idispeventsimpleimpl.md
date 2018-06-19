---
title: IDispEventSimpleImpl (ATL)를 사용 하 여 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- IDispEventSimpleImpl
dev_langs:
- C++
helpviewer_keywords:
- IDispEventSimpleImpl class, using
ms.assetid: 8640ad1a-4bd0-40a5-b5e4-7322685d7aab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0cdef5012288b7f5f17040f73dfac5ec1f90d4f0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32361953"
---
# <a name="using-idispeventsimpleimpl"></a>IDispEventSimpleImpl를 사용 하 여
사용 하는 경우 `IDispEventSimpleImpl` 이벤트를 처리 하려면 해야 합니다.  
  
-   클래스를 파생 [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md)합니다.  
  
-   이벤트 싱크 맵 클래스에 추가 합니다.  
  
-   정의 [_ATL_FUNC_INFO](../atl/reference/atl-func-info-structure.md) 이벤트를 설명 하는 구조입니다.  
  
-   항목을 사용 하 여 이벤트 싱크 맵 추가 [SINK_ENTRY_INFO](reference/composite-control-macros.md#sink_entry_info) 매크로입니다.  
  
-   처리에 관심이 메서드를 구현 합니다.  
  
-   싱 및 이벤트 소스가 unadvise 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 처리 하는 방법을 보여 줍니다.는 **DocumentChange** 이벤트가 Word의 **응용 프로그램** 개체입니다. 이 이벤트가 메서드로 정의 된는 **ApplicationEvents** dispinterface 합니다.  
  
 이 예제에서는 [ATLEventHandling 샘플](../visual-cpp-samples.md)합니다.  
  
 `[`  
  
 `uuid(000209F7-0000-0000-C000-000000000046),`  
  
 `hidden`  
  
 `]`  
  
 `dispinterface ApplicationEvents {`  
  
 `properties:`  
  
 `methods:`  
  
 `[id(0x00000001), restricted, hidden]`  
  
 `void Startup();`  
  
 `[id(0x00000002)]`  
  
 `void Quit();`  
  
 `[id(0x00000003)]`  
  
 `void DocumentChange();`  
  
 `};`  
  
 이 예제에서는 사용 `#import` Word의 형식 라이브러리에서 필요한 헤더 파일을 생성 하도록 합니다. 이 예제 Word의 다른 버전과 함께 사용 하려는 경우에 올바른 mso dll 파일을 지정 해야 합니다. 예를 들어 Office 2000 mso9.dll을 제공 하 고 OfficeXP mso.dll을 제공 합니다. 이 코드는 stdafx.h에서 간소화 됩니다.  
  
 [!code-cpp[NVC_ATL_EventHandlingSample#1](../atl/codesnippet/cpp/using-idispeventsimpleimpl_1.h)]  
  
 이 예제에 실제로 사용 된 형식 라이브러리에서 유일한 정보는 Word의 CLSID **응용 프로그램** 개체와의 IID는 **ApplicationEvents** 인터페이스입니다. 이 정보는 컴파일 타임에만 사용 됩니다.  
  
 다음 코드 Simple.h에 나타납니다. 관련 코드 주석으로 표시 됩니다.  
  
 [!code-cpp[NVC_ATL_EventHandlingSample#3](../atl/codesnippet/cpp/using-idispeventsimpleimpl_2.h)]  
  
 다음 코드는 Simple.cpp에서:  
  
 [!code-cpp[NVC_ATL_EventHandlingSample#4](../atl/codesnippet/cpp/using-idispeventsimpleimpl_3.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [이벤트 처리](../atl/event-handling-and-atl.md)   
 [ATLEventHandling 샘플](../visual-cpp-samples.md)

