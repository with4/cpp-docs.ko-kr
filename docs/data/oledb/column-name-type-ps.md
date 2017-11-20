---
title: COLUMN_NAME_TYPE_PS | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: COLUMN_NAME_TYPE_PS
dev_langs: C++
helpviewer_keywords: COLUMN_NAME_TYPE_PS macro
ms.assetid: 99df7e33-47fc-48ec-ad03-5fd03a190aa9
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: cc2901b944cb7074b18aed2d583cc9dcfac9a345
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="columnnametypeps"></a>COLUMN_NAME_TYPE_PS
행 집합의 특정 열에는 행 집합의 바인딩을 나타냅니다. 비슷한 [COLUMN_NAME](../../data/oledb/column-name.md)제외 하 고이 매크로 또한 데이터 형식, 정밀도 및 배율을 사용 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
COLUMN_NAME_TYPE_PS(  
pszName  
,   
wType  
,   
nPrecision  
,   
nScale  
,   
data  
 )  
  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pszName`  
 [in] 열 이름에 대 한 포인터입니다. 이름에는 유니코드 문자열 이어야 합니다. 예를 들어, 이름 앞에 'L'을 배치 하 여이 수행할 수 있습니다: `L"MyColumn"`합니다.  
  
 `wType`  
 [in] 데이터 형식입니다.  
  
 `nPrecision`  
 [in] 데이터를 가져올 때 사용 하는 최대 전체 자릿수 및 `wType` 은 `DBTYPE_NUMERIC`합니다. 그렇지 않으면이 매개 변수는 무시 됩니다.  
  
 `nScale`  
 [in] 데이터를 가져올 때 사용할 소수 자릿수 및 `wType` 은 `DBTYPE_NUMERIC` 또는 **DBTYPE_DECIMAL**합니다.  
  
 `data`  
 [in] 사용자 레코드에서 해당 데이터 멤버입니다.  
  
## <a name="remarks"></a>설명  
 참조 [COLUMN_NAME](../../data/oledb/column-name.md) 위치 대 한 정보는 **COLUMN_NAME_\***  매크로 사용 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [매크로 및 전역 함수에 대 한 OLE DB 소비자 템플릿](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md)   
 [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md)   
 [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md)   
 [COLUMN_NAME](../../data/oledb/column-name.md)   
 [COLUMN_NAME_EX](../../data/oledb/column-name-ex.md)   
 [COLUMN_NAME_LENGTH](../../data/oledb/column-name-length.md)   
 [COLUMN_NAME_LENGTH_STATUS](../../data/oledb/column-name-length-status.md)   
 [COLUMN_NAME_STATUS](../../data/oledb/column-name-status.md)   
 [COLUMN_NAME_PS](../../data/oledb/column-name-ps.md)   
 [COLUMN_NAME_PS_LENGTH](../../data/oledb/column-name-ps-length.md)   
 [COLUMN_NAME_PS_STATUS](../../data/oledb/column-name-ps-status.md)   
 [COLUMN_NAME_PS_LENGTH_STATUS](../../data/oledb/column-name-ps-length-status.md)   
 [COLUMN_NAME_TYPE](../../data/oledb/column-name-type.md)   
 [COLUMN_NAME_TYPE_SIZE](../../data/oledb/column-name-type-size.md)   
 [COLUMN_NAME_TYPE_STATUS](../../data/oledb/column-name-type-status.md)