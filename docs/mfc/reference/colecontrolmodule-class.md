---
title: "COleControlModule 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- OleControlModule
dev_langs:
- C++
helpviewer_keywords:
- OLE control modules [MFC]
- MFC ActiveX controls [MFC], OLE control modules
- COleControlModule class [MFC]
- control modules [MFC]
ms.assetid: 0721724d-d4af-4eda-ad34-5a2b27810dd4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 196b69a0d86c3809415e030adb567c8642051f40
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="colecontrolmodule-class"></a>COleControlModule 클래스
OLE 컨트롤 모듈 개체를 파생하는 기본 클래스입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class COleControlModule : public CWinApp  
```  
  
## <a name="remarks"></a>설명  
 이 클래스는 제어 모듈을 초기화 하기 위한 멤버 함수를 제공 합니다. Microsoft Foundation classes를 사용 하는 각 OLE 컨트롤 모듈 개체에서 파생 된 포함할 수 있습니다 `COleControlModule`합니다. 이 개체는 다른 c + +의 전역 개체 생성 될 때 생성 됩니다. 파생 사용자 선언 `COleControlModule` 전역 수준에서 개체입니다.  
  
 사용 하 여 대 한 자세한 내용은 `COleControlModule` 클래스를 참조 하십시오.는 [CWinApp](../../mfc/reference/cwinapp-class.md) 클래스 및 문서 [ActiveX 컨트롤](../../mfc/mfc-activex-controls.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWinThread](../../mfc/reference/cwinthread-class.md)  
  
 [CWinApp](../../mfc/reference/cwinapp-class.md)  
  
 `COleControlModule`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxctl.h  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 TESTHELP](../../visual-cpp-samples.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)



