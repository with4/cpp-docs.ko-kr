---
title: 'Cbookmark:: Setbookmark | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CBookmark<0>::SetBookmark
- ATL.CBookmark<0>.SetBookmark
- CBookmark<0>.SetBookmark
- SetBookmark
- ATL::CBookmark::SetBookmark
- ATL::CBookmark<0>::SetBookmark
- CBookmark.SetBookmark
- ATL.CBookmark.SetBookmark
- CBookmark::SetBookmark
dev_langs:
- C++
helpviewer_keywords:
- SetBookmark method
ms.assetid: bcd26831-6045-4e69-96d6-abf8037fc18d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 6d8f4402a6caf01f4d813e6ee8f9fd2d95512394
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33093679"
---
# <a name="cbookmarksetbookmark"></a>CBookmark::SetBookmark
참조 하는 책갈피 값 복사 `pBuffer` 에 `CBookmark` 버퍼링 및 버퍼 크기를 설정 `nSize`합니다.  
  
## <a name="syntax"></a>구문  
  
```
HRESULT SetBookmark(DBLENGTH nSize,  
  BYTE* pBuffer) throw();  
```  
  
#### <a name="parameters"></a>매개 변수  
 *nSize*  
 [in] 책갈피 버퍼의 크기입니다.  
  
 `pBuffer`  
 [in] 책갈피 값을 포함 하는 바이트 배열에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 표준 `HRESULT`입니다.  
  
## <a name="remarks"></a>설명  
 이 함수는 영어로 **CBookmark\<0 >** 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CBookmark 클래스](../../data/oledb/cbookmark-class.md)