---
title: CD2DSizeU 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CD2DSizeU
- AFXRENDERTARGET/CD2DSizeU
- AFXRENDERTARGET/CD2DSizeU::CD2DSizeU
- AFXRENDERTARGET/CD2DSizeU::IsNull
dev_langs:
- C++
helpviewer_keywords:
- CD2DSizeU [MFC], CD2DSizeU
- CD2DSizeU [MFC], IsNull
ms.assetid: 6e679ba8-2112-43c3-8275-70b660856f02
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fa7c42216f55479050812b559f533829d55162b9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33349937"
---
# <a name="cd2dsizeu-class"></a>CD2DSizeU 클래스
D2D1_SIZE_U에 대 한 래퍼입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CD2DSizeU : public D2D1_SIZE_U;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CD2DSizeU::CD2DSizeU](#cd2dsizeu)|오버로드됨. 생성 된 `CD2DSizeU` 에서 개체 `D2D1_SIZE_U` 개체입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CD2DSizeU::IsNull](#isnull)|반환 된 `boolean` 유효 하지 않은 데이터 식에 포함 되어 있는지 여부를 나타내는 값 ( `null`).|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CD2DSizeU::operator CSize](#operator_csize)|변환 `CD2DSizeU` 를 `CSize` 개체입니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `D2D1_SIZE_U`  
  
 [CD2DSizeU](../../mfc/reference/cd2dsizeu-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxrendertarget.h  
  
##  <a name="cd2dsizeu"></a>  CD2DSizeU::CD2DSizeU  
 CD2DSizeU CSize 개체에서 개체를 만듭니다.  
  
```  
CD2DSizeU(const CSize& size);  
CD2DSizeU(const D2D1_SIZE_U& size);  
  CD2DSizeU(const D2D1_SIZE_U* size);

 
CD2DSizeU(
    UINT32 cx = 0,  
    UINT32 cy = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 `size`  
 소스 크기  
  
 `cx`  
 소스 너비  
  
 `cy`  
 원본 높이  
  
##  <a name="isnull"></a>  CD2DSizeU::IsNull  
 식에 유효 하지 않은 데이터 (Null)이 포함 되어 있는지 여부를 나타내는 부울 값을 반환 합니다.  
  
```  
BOOL IsNull() const;  
```  
  
### <a name="return-value"></a>반환 값  
 너비와 높이; 비어 있으면 TRUE입니다. 그렇지 않으면 FALSE입니다.  
  
##  <a name="operator_csize"></a>  CD2DSizeU::operator CSize  
 CD2DSizeU CSize 개체로 변환합니다.  
  
```  
operator CSize();
```   
  
### <a name="return-value"></a>반환 값  
 D2D 크기의 현재 값입니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)
