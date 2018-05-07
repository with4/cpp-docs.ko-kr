---
title: CUserException 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CUserException
dev_langs:
- C++
helpviewer_keywords:
- operations [MFC], stopping
- exceptions [MFC], throwing
- CUserException class [MFC]
- errors [MFC], trapping
- operations [MFC]
- throwing exceptions [MFC], stopping user operations
ms.assetid: 2156ba6d-2cce-415a-9000-6f02c26fcd7d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a1701f6894ba3b44205526c59bad7ef635c1bbbd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="cuserexception-class"></a>CUserException 클래스
최종 사용자 작업을 중지하도록 throw됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CUserException : public CSimpleException  
```  
  
## <a name="remarks"></a>설명  
 사용 하 여 `CUserException` 응용 프로그램별 예외에 대 한 throw/catch 예외 메커니즘을 사용 하려는 경우. "User" 클래스 이름에 "내 사용자가 처리 해야 하는 예외입니다."으로 해석 될 수 있습니다.  
  
 A `CUserException` 전역 함수를 호출한 후 일반적으로 예외가 `AfxMessageBox` 는 작업이 실패 했습니다 사용자에 게 통보 합니다. 예외 처리기를 작성할 때 사용자는 일반적으로 이미 अ ध 오류 때문에 특별히 예외를 처리 합니다. 프레임 워크는 경우에 따라이 예외를 throw 합니다. throw 한 `CUserException` 다음과 같은 경고를 직접 및 전역 함수를 호출할 `AfxThrowUserException`합니다.  
  
 아래 예제에서 오류가 발생할 수 있는 작업을 포함 하는 함수 경고 메시지를 표시 하 고 throw 된 `CUserException`합니다. 호출 하는 함수는 예외를 catch 하 고 특수 처리:  
  
 [!code-cpp[NVC_MFCExceptions#24](../../mfc/codesnippet/cpp/cuserexception-class_1.cpp)]  
  
 사용 하 여 대 한 자세한 내용은 `CUserException`, 문서를 참조 [예외 처리 (MFC)](../../mfc/exception-handling-in-mfc.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 [CSimpleException](../../mfc/reference/csimpleexception-class.md)  
  
 `CUserException`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxwin.h  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CException 클래스](../../mfc/reference/cexception-class.md)
