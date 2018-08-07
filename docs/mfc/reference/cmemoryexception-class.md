---
title: CMemoryException 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMemoryException
- AFX/CMemoryException
- AFX/CMemoryException::CMemoryException
dev_langs:
- C++
helpviewer_keywords:
- CMemoryException [MFC], CMemoryException
ms.assetid: 9af0ed57-d12a-45ca-82b5-c910a60f7edf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 12971af6bed7c04c6f6f214f0b583a4f7e6eb7a1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33366306"
---
# <a name="cmemoryexception-class"></a>CMemoryException 클래스
메모리 부족 예외 상태를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMemoryException : public CSimpleException  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CMemoryException::CMemoryException](#cmemoryexception)|`CMemoryException` 개체를 생성합니다.|  
  
## <a name="remarks"></a>설명  
 더 이상 자격 없음은 불필요 하거나 가능한 합니다. 메모리 예외가 자동으로 **새**합니다. 메모리 함수를 직접 작성 하는 경우 사용 하 여 `malloc`, 다음 예제는 메모리 예외를 throw 하는 일을 담당 합니다.  
  
 대 한 자세한 내용은 `CMemoryException`, 문서를 참조 [예외 처리 (MFC)](../../mfc/exception-handling-in-mfc.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 [CSimpleException](../../mfc/reference/csimpleexception-class.md)  
  
 `CMemoryException`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afx.h  
  
##  <a name="cmemoryexception"></a>  CMemoryException::CMemoryException  
 `CMemoryException` 개체를 생성합니다.  
  
```  
CMemoryException();  
```  
  
### <a name="remarks"></a>설명  
 이 생성자를 직접 사용 하지 않고 전역 함수를 호출 하는 대신 [AfxThrowMemoryException](exception-processing.md#afxthrowmemoryexception)합니다. 이전에 할당 된 메모리에 있는 예외 개체를 생성 하므로이 전역 함수는 메모리 부족 상황에 성공할 수 있습니다. 예외 처리에 대 한 자세한 내용은 문서 참조 [예외](../exception-handling-in-mfc.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CException 클래스](cexception-class.md)   
 [계층 구조 차트](../hierarchy-chart.md)



