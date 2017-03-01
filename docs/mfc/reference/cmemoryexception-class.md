---
title: "CMemoryException 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMemoryException
dev_langs:
- C++
helpviewer_keywords:
- CMemoryException class
- memory exceptions
- exceptions, memory type
- C++ exception handling, memory
- memory, exception handling
ms.assetid: 9af0ed57-d12a-45ca-82b5-c910a60f7edf
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
ms.openlocfilehash: 87be1b16d546791d24bbffa62207ec9ccb350139
ms.lasthandoff: 02/24/2017

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
  
## <a name="remarks"></a>주의  
 더 이상 없는 한정 가능한 것은 필요 합니다. 메모리 예외가 자동으로 **새**합니다. 고유한 메모리 함수를 작성 하는 경우 사용 하 여 `malloc`, 다음 예제는 메모리 예외를 throw 하는 일을 담당 합니다.  
  
 대 한 자세한 내용은 `CMemoryException`, 문서를 참조 하십시오 [예외 처리 (MFC)](../../mfc/exception-handling-in-mfc.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 [CSimpleException](../../mfc/reference/csimpleexception-class.md)  
  
 `CMemoryException`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afx.h  
  
##  <a name="a-namecmemoryexceptiona--cmemoryexceptioncmemoryexception"></a><a name="cmemoryexception"></a>CMemoryException::CMemoryException  
 `CMemoryException` 개체를 생성합니다.  
  
```  
CMemoryException();  
```  
  
### <a name="remarks"></a>주의  
 이 생성자를 직접 사용 하지 않고 대신 전역 함수를 호출 [AfxThrowMemoryException](exception-processing.md#afxthrowmemoryexception)합니다. 이 전역 함수는 이전에 할당 된 메모리에 있는 예외 개체를 생성 하기 때문에 메모리 부족 상황에서 성공할 수 있습니다. 예외 처리에 대 한 자세한 내용은 문서를 참조 하십시오. [예외](../exception-handling-in-mfc.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CException 클래스](cexception-class.md)   
 [계층 구조 차트](../hierarchy-chart.md)




