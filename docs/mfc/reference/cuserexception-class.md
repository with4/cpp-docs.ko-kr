---
title: "CUserException 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CUserException
dev_langs:
- C++
helpviewer_keywords:
- operations [C++], stopping
- exceptions, throwing
- CUserException class
- errors [C++], trapping
- operations [C++]
- throwing exceptions, stopping user operations
ms.assetid: 2156ba6d-2cce-415a-9000-6f02c26fcd7d
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5187996fc377bca8633360082d07f7ec8a68ee57
ms.openlocfilehash: 8548ffa7ad9032e174d650e210a70a29b0e3f19d
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="cuserexception-class"></a>CUserException 클래스
최종 사용자 작업을 중지하도록 throw됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CUserException : public CSimpleException  
```  
  
## <a name="remarks"></a>주의  
 사용 하 여 `CUserException` 응용 프로그램별 예외에 대 한 throw/catch 예외 메커니즘을 사용 하려는 경우. "User" 클래스 이름에 "내 사용자가 처리 해야 하는 예외입니다."으로 해석 될 수 있습니다.  
  
 A `CUserException` 전역 함수를 호출한 후 일반적으로 예외가 `AfxMessageBox` 는 작업이 실패 했습니다 사용자에 게 있습니다. 예외 처리기를 작성할 때 사용자 일반적으로 이미 보고 된 오류 때문에 특수 예외를 처리 합니다. 일부 경우에이 예외를 throw 하는 프레임 워크입니다. Throw 하는 `CUserException` 사용자 및 전역 함수를 호출할 사용자가 직접 `AfxThrowUserException`합니다.  
  
 아래 예제에서 오류가 발생할 수 있는 작업을 포함 하는 함수 경고 메시지를 표시 하 고 throw 된 `CUserException`합니다. 호출 함수는 예외를 catch 하 고 특별 하 게이 처리 합니다.  
  
 [!code-cpp[NVC_MFCExceptions #&24;](../../mfc/codesnippet/cpp/cuserexception-class_1.cpp)]  
  
 사용 하 여 대 한 자세한 내용은 `CUserException`, 문서를 참조 하십시오 [예외 처리 (MFC)](../../mfc/exception-handling-in-mfc.md)합니다.  
  
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

