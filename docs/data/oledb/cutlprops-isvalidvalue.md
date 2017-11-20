---
title: 'Cutlprops:: Isvalidvalue | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CUtlProps::IsValidValue
- CUtlProps.IsValidValue
- IsValidValue
dev_langs: C++
helpviewer_keywords: IsValidValue method
ms.assetid: 1164556e-8d98-429c-a396-fc9a699e0e97
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a33a19a24504898ffb9e0d9b9d5c7c23fcef4efc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="cutlpropsisvalidvalue"></a>CUtlProps::IsValidValue
값 속성을 설정 하기 전에 유효성을 검사 하는 데 사용 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      virtual HRESULT CUtlPropsBase::IsValidValue(  
   ULONG /* iCurSet */,  
   DBPROP* pDBProp   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `iCurSet`  
 속성 집합 배열;에 대 한 인덱스 하나의 속성 집합이 있는 경우 0입니다.  
  
 `pDBProp`  
 속성 ID와에 새 값을 [DBPROP](https://msdn.microsoft.com/en-us/library/ms717970.aspx) 구조입니다.  
  
## <a name="return-value"></a>반환 값  
 표준 `HRESULT`입니다. 기본 반환 값은 `S_OK`합니다.  
  
## <a name="remarks"></a>설명  
 모든 유효성 검사 루틴을 사용 하 여 속성을 설정 하려고 하는 값에 실행 하려는 경우이 함수를 재정의 해야 합니다. 확인할 수는 예를 들어 **DBPROP_AUTH_PASSWORD** 유효한 값을 결정 하려면 암호 테이블에 대 한 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [CUtlProps 클래스](../../data/oledb/cutlprops-class.md)