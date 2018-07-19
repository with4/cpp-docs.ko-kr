---
title: 포함 된 Windows를 사용 하 여 | Microsoft Docs
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
ms.openlocfilehash: cc17925e36e0e224a657177d0aa18912c564efed
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/05/2018
ms.locfileid: "37850802"
---
# <a name="using-contained-windows"></a>포함 된 Windows를 사용 하 여
포함 된 windows를 구현 하는 ATL [CContainedWindowT](../atl/reference/ccontainedwindowt-class.md)합니다. 포함된 된 창을 해당 메시지는 자체 클래스에서 처리 하는 대신 컨테이너 개체를 위임 하는 창을 나타냅니다.  
  
> [!NOTE]
>  클래스를 파생 해야 `CContainedWindowT` 포함 된 windows를 사용 하려면.  
  
 포함 된 windows를 사용 하 여 기존 Windows 클래스 또는 기존 창 하위 클래스입니다. 슈퍼 있습니다. 슈퍼를 기존 Windows 창을 만들려면 클래스, 먼저 이름을 기존 클래스의 생성자에 지정 된 `CContainedWindowT` 개체. 그런 다음 호출 `CContainedWindowT::Create`합니다. 기존 창 하위 클래스에 Windows 클래스 이름 (생성자에 NULL 전달)를 지정할 필요가 없습니다. 호출 된 `CContainedWindowT::SubclassWindow` 서브클래싱 되는 창에 대 한 핸들을 사용 하 여 메서드.  
  
 일반적으로 포함 된 windows 컨테이너 클래스의 데이터 멤버로 사용 합니다. 컨테이너는 창이; 될 필요가 없습니다. 그러나 파생 되어야 합니다 [CMessageMap](../atl/reference/cmessagemap-class.md)합니다.  
  
 포함된 된 창을 대체 메시지 맵을 사용 하 여 해당 메시지를 처리할 수 있습니다. 둘 이상의 포함 된 창에 있는 경우 포함 된 별도 창에 해당 하는 메시지 맵, 여러 개의 대체를 선언 해야 합니다.  
  
## <a name="example"></a>예  
 다음은 두 개의 포함 된 windows 컨테이너 클래스의 예입니다.  
  
 [!code-cpp[NVC_ATL_Windowing#67](../atl/codesnippet/cpp/using-contained-windows_1.h)]  
  
 포함 된 창에 대 한 자세한 내용은 참조는 [SUBEDIT](../visual-cpp-samples.md) 샘플입니다.  
  
## <a name="see-also"></a>참고 항목  
 [창 클래스](../atl/atl-window-classes.md)

