---
title: 포함 된 창을 사용 하 여 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ATL, windows
- windows [C++], ATL
- contained windows in ATL
ms.assetid: 7b3d79e5-b569-413f-9b98-df4f14efbe2b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f6c3b439baf05c4e4287613e9b6b5a9b1c2546b6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32357923"
---
# <a name="using-contained-windows"></a>포함 된 창 사용
ATL 구현으로 포함 된 창을 [CContainedWindowT](../atl/reference/ccontainedwindowt-class.md)합니다. 포함 된 창을는 해당 메시지는 자체 클래스에서 처리 하는 대신 컨테이너 개체를 위임 하는 창을 나타냅니다.  
  
> [!NOTE]
>  클래스를 파생 해야 `CContainedWindowT` 하려면 포함 된 창을 사용 합니다.  
  
 포함 된 창 기존 Windows 클래스 또는 서브 클래스는 기존 창 슈퍼 수 있습니다. 슈퍼 기존 Windows 창을 만들기 위해 클래스, 먼저 기존 클래스 이름에 대 한 생성자에 지정 된 `CContainedWindowT` 개체입니다. 그런 다음 호출 `CContainedWindowT::Create`합니다. 기존 창 서브 클래스에 Windows 클래스 이름을 지정할 필요가 없습니다 (전달 **NULL** 생성자에). 호출 하기만 하면는 `CContainedWindowT::SubclassWindow` 메서드 서브클래싱된 되 고 창에 핸들을 포함 합니다.  
  
 일반적으로 컨테이너 클래스의 데이터 멤버로 포함 된 창을 사용 합니다. 컨테이너 창; 될 필요가 없습니다. 하지만 파생 되어야 [CMessageMap](../atl/reference/cmessagemap-class.md)합니다.  
  
 포함된 된 창을 해당 메시지를 처리할 대체 메시지 맵을 사용할 수 있습니다. 포함 된 창이 여러 개 있는 경우 여러 개의 별도 포함 된 창에 해당 하는 메시지 맵 대체 선언 해야 합니다.  
  
## <a name="example"></a>예제  
 다음은 두 개의 포함 된 창 사용 하는 컨테이너 클래스의 예입니다.  
  
 [!code-cpp[NVC_ATL_Windowing#67](../atl/codesnippet/cpp/using-contained-windows_1.h)]  
  
 포함 된 기간에 대 한 자세한 내용은 참조는 [SUBEDIT](../visual-cpp-samples.md) 샘플.  
  
## <a name="see-also"></a>참고 항목  
 [창 클래스](../atl/atl-window-classes.md)

