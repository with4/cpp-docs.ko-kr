---
title: CResourceException 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CResourceException
- AFXWIN/CResourceException
- AFXWIN/CResourceException::CResourceException
dev_langs:
- C++
helpviewer_keywords:
- CResourceException [MFC], CResourceException
ms.assetid: af6ae043-d124-4bfd-b35e-7bb0db67d289
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6fdbfb29b00eaac40b4da2b78753df6a0596764f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33371532"
---
# <a name="cresourceexception-class"></a>CResourceException 클래스
Windows에서 요청된 리소스를 찾거나 할당할 수 없을 경우 발생합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CResourceException : public CSimpleException  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CResourceException::CResourceException](#cresourceexception)|`CResourceException` 개체를 생성합니다.|  
  
## <a name="remarks"></a>설명  
 더 이상 자격 없음은 불필요 하거나 가능한 합니다.  
  
 사용 하 여 대 한 자세한 내용은 `CResourceException`, 문서를 참조 [예외 처리 (MFC)](../../mfc/exception-handling-in-mfc.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 [CSimpleException](../../mfc/reference/csimpleexception-class.md)  
  
 `CResourceException`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxwin.h  
  
##  <a name="cresourceexception"></a>  CResourceException::CResourceException  
 `CResourceException` 개체를 생성합니다.  
  
```  
CResourceException();
```  
  
### <a name="remarks"></a>설명  
 이 생성자를 직접 사용 하지 않고 전역 함수를 호출 하는 대신 [AfxThrowResourceException](exception-processing.md#afxthrowresourceexception)합니다. 예외에 대 한 자세한 내용은 문서 참조 [MFC의 예외 처리](../exception-handling-in-mfc.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CException 클래스](cexception-class.md)   
 [계층 구조 차트](../hierarchy-chart.md)


