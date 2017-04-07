---
title: "CNotSupportedException 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CNotSupportedException
- AFX/CNotSupportedException
- AFX/CNotSupportedException::CNotSupportedException
dev_langs:
- C++
helpviewer_keywords:
- CNotSupportedException class
- unsupported features
- exceptions, not supported
ms.assetid: e517391b-eb94-4c39-ae32-87b45bf7d624
caps.latest.revision: 20
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 6cb66448d0dadaf1f70c3606bc1b9027bd217a38
ms.lasthandoff: 02/24/2017

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
  
## <a name="remarks"></a>주의  
 더 이상 없는 한정 가능한 것은 필요 합니다.  
  
 사용 하 여 대 한 자세한 내용은 `CNotSupportedException`, 문서를 참조 하십시오 [예외 처리 (MFC)](../../mfc/exception-handling-in-mfc.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 [CSimpleException](../../mfc/reference/csimpleexception-class.md)  
  
 `CNotSupportedException`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afx.h  
  
##  <a name="cnotsupportedexception"></a>CNotSupportedException::CNotSupportedException  
 `CNotSupportedException` 개체를 생성합니다.  
  
```  
CNotSupportedException();
```  
  
### <a name="remarks"></a>주의  
 이 생성자를 직접 사용 하지 않고 대신 전역 함수를 호출 [AfxThrowNotSupportedException](exception-processing.md#afxthrownotsupportedexception)합니다. 예외 처리에 대 한 자세한 내용은 문서를 참조 하십시오. [MFC의 예외 처리](../exception-handling-in-mfc.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CException 클래스](cexception-class.md)   
 [계층 구조 차트](../hierarchy-chart.md)



