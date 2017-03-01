---
title: "COleControlModule 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleControlModule
dev_langs:
- C++
helpviewer_keywords:
- OLE control modules
- MFC ActiveX controls, OLE control modules
- COleControlModule class
- control modules
ms.assetid: 0721724d-d4af-4eda-ad34-5a2b27810dd4
caps.latest.revision: 23
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 5c6fbfc8699d7d66c40b0458972d8b6ef0dcc705
ms.openlocfilehash: 2e77c386875d25f47f0cc07eb3b7d315f1678c56
ms.lasthandoff: 02/24/2017

---
# <a name="colecontrolmodule-class"></a>COleControlModule 클래스
OLE 컨트롤 모듈 개체를 파생하는 기본 클래스입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class COleControlModule : public CWinApp  
```  
  
## <a name="remarks"></a>주의  
 이 클래스는 제어 모듈을 초기화 하기 위한 멤버 함수를 제공 합니다. Microsoft Foundation 클래스를 사용 하는 각 OLE 컨트롤 모듈에서 파생 된 개체를 하나 포함할 수 있습니다 `COleControlModule`합니다. 이 개체는 다른 c + +의 전역 개체 생성 될 때 생성 됩니다. 파생 된 선언 `COleControlModule` 전역 수준에서 개체입니다.  
  
 사용 하 여 대 한 자세한 내용은 `COleControlModule` 클래스를 참조는 [CWinApp](../../mfc/reference/cwinapp-class.md) 클래스 및 문서 [ActiveX 컨트롤](../../mfc/mfc-activex-controls.md)합니다.  
  
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




