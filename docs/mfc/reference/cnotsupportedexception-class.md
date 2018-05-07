---
title: CNotSupportedException 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CNotSupportedException
- AFX/CNotSupportedException
- AFX/CNotSupportedException::CNotSupportedException
dev_langs:
- C++
helpviewer_keywords:
- CNotSupportedException [MFC], CNotSupportedException
ms.assetid: e517391b-eb94-4c39-ae32-87b45bf7d624
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 510f9db4a7e5688df76baafa868846fd1614f584
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="cnotsupportedexception-class"></a>CNotSupportedException 클래스
지원되지 않는 기능을 요청한 결과인 예외를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CNotSupportedException : public CSimpleException  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CNotSupportedException::CNotSupportedException](#cnotsupportedexception)|`CNotSupportedException` 개체를 생성합니다.|  
  
## <a name="remarks"></a>설명  
 더 이상 자격 없음은 불필요 하거나 가능한 합니다.  
  
 사용 하 여 대 한 자세한 내용은 `CNotSupportedException`, 문서를 참조 [예외 처리 (MFC)](../../mfc/exception-handling-in-mfc.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 [CSimpleException](../../mfc/reference/csimpleexception-class.md)  
  
 `CNotSupportedException`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afx.h  
  
##  <a name="cnotsupportedexception"></a>  CNotSupportedException::CNotSupportedException  
 `CNotSupportedException` 개체를 생성합니다.  
  
```  
CNotSupportedException();
```  
  
### <a name="remarks"></a>설명  
 이 생성자를 직접 사용 하지 않고 전역 함수를 호출 하는 대신 [AfxThrowNotSupportedException](exception-processing.md#afxthrownotsupportedexception)합니다. 예외 처리에 대 한 자세한 내용은 문서 참조 [MFC의 예외 처리](../exception-handling-in-mfc.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CException 클래스](cexception-class.md)   
 [계층 구조 차트](../hierarchy-chart.md)


