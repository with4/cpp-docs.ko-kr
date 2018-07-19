---
title: 복합 컨트롤에 기능 추가 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- event handlers [C++], ActiveX controls
- composite controls, handling events
- ActiveX controls [C++], events
ms.assetid: 98f85681-9564-480d-af38-03f9733fe58b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 67602e16fc5a30c82e82772b6b9f6c553ba79d9b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32354184"
---
# <a name="adding-functionality-to-the-composite-control"></a>복합 컨트롤에 기능 추가
복합 컨트롤에 필요한 컨트롤을 삽입 하면 다음 단계는 새로운 기능을 추가 해야 합니다. 이 새로운 기능은 일반적으로 두 가지 범주에 해당 됩니다.  
  
-   특정 기능을 사용 하 여 복합 컨트롤의 동작을 사용자 지정 / 추가 인터페이스를 지원 합니다.  
  
-   포함 된 ActiveX 컨트롤 (또는 컨트롤)에서 이벤트를 처리 합니다.  
  
 용도이 문서의 범위에 대 한이 섹션의 나머지 부분에서는 ActiveX 컨트롤에서 보낸 이벤트 처리에 중점을 둡니다.  
  
> [!NOTE]
>  Windows 컨트롤에서 메시지를 처리 해야 하는 경우 참조 [창 구현](../atl/implementing-a-window.md) ATL에서 처리 하는 메시지에 대 한 자세한 내용은  
  
 ActiveX 컨트롤에서 대화 상자 리소스를 삽입 한 후 컨트롤을 마우스 오른쪽 단추로 클릭 하 고 클릭 **이벤트 처리기 추가**합니다. 처리 하 고 클릭 이벤트를 선택 **추가 및 편집**합니다. 이벤트 처리기 코드는 컨트롤의.h 파일에 추가 됩니다.  
  
 복합 컨트롤에 ActiveX 컨트롤에 대 한 연결 지점을 자동으로 연결 되 고 호출을 통해 연결이 끊어진 [CComCompositeControl::AdviseSinkMap](../atl/reference/ccomcompositecontrol-class.md#advisesinkmap)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [복합 컨트롤 기본 사항](../atl/atl-composite-control-fundamentals.md)

