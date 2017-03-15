---
title: "CMFCAcceleratorKey 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCAcceleratorKey
dev_langs:
- C++
helpviewer_keywords:
- CMFCAcceleratorKey class
ms.assetid: d140fbf7-23db-45ea-a63e-414a5ec7b3d5
caps.latest.revision: 36
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 7baa210acfabe8f17e2ab747fd98fe463c2907a2
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcacceleratorkey-class"></a>CMFCAcceleratorKey 클래스
가상 키 매핑 및 서식을 구현 하는 도우미 클래스입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMFCAcceleratorKey : public CObject  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCAcceleratorKey::CMFCAcceleratorKey](#cmfcacceleratorkey)|`CMFCAcceleratorKey` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCAcceleratorKey::Format](#format)|바로 가기 키 구조를 시각적 표현으로 변환합니다.|  
|[CMFCAcceleratorKey::SetAccelerator](#setaccelerator)|바로 가기 키를 설정 하는 `CMFCAcceleratorKey` 개체입니다.|  
  
## <a name="remarks"></a>주의  
 액셀러레이터 키 바로 가기 키 라고도 합니다. 사용자가 바로 가기 키를 표시 하려는 경우는 [CMFCAcceleratorKeyAssignCtrl 클래스](../../mfc/reference/cmfcacceleratorkeyassignctrl-class.md) 지도 키보드 바로 가기, Alt + Shift + S와 같은 "Alt + Shift + S"와 같은 사용자 지정 텍스트 형식으로. 각 `CMFCAcceleratorKey` 개체를 텍스트 형식으로 단일 바로 가기 키를 매핑합니다.  
  
 바로 가기 키와 액셀러레이터 키 테이블을 사용 하는 방법에 대 한 자세한 내용은 참조 [CKeyboardManager 클래스](../../mfc/reference/ckeyboardmanager-class.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 생성 하는 방법을 한 `CMFCAcceleratorKey` 개체 및이 방법을 사용 하 여 해당 `Format` 메서드.  
  
 [!code-cpp[NVC_MFC_RibbonApp #&30;](../../mfc/reference/codesnippet/cpp/cmfcacceleratorkey-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMFCAcceleratorKey`   
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxacceleratorkey.h  
  
##  <a name="a-namecmfcacceleratorkeya--cmfcacceleratorkeycmfcacceleratorkey"></a><a name="cmfcacceleratorkey"></a>CMFCAcceleratorKey::CMFCAcceleratorKey  
 생성 된 [CMFCAcceleratorKey](../../mfc/reference/cmfcacceleratorkey-class.md) 개체입니다.  
  
```  
CMFCAcceleratorKey();  
CMFCAcceleratorKey(LPACCEL lpAccel);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpAccel`  
 바로 가기 키에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
 만들 때 바로 가기 키를 제공 하지 않으면 한 `CMFCAccleratorKey`를 사용 하 여는 [CMFCAcceleratorKey::SetAccelerator](#setaccelerator) 된 바로 가기 키를 연결 하는 방법이 프로그램 `CMFCAcceleratorKey` 개체입니다.  
  
##  <a name="a-nameformata--cmfcacceleratorkeyformat"></a><a name="format"></a>CMFCAcceleratorKey::Format  
 바로 가기 키 구조를 연결 된 문자열 값으로 변환합니다.  
  
```  
void Format(CString& str) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [out] `str`  
 에 대 한 참조는 `CString` 개체 메서드는 번역 된 바로 가기 키를 기록 하는 위치입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 관련 된 바로 가기 키의 문자열 형식을 검색합니다. 문자열 형식을 설정할 수는 [CMFCAcceleratorKey](../../mfc/reference/cmfcacceleratorkey-class.md) 메서드 또는 생성자를 사용 하 여 [CMFCAcceleratorKey::SetAccelerator](#setaccelerator)합니다.  
  
##  <a name="a-namesetacceleratora--cmfcacceleratorkeysetaccelerator"></a><a name="setaccelerator"></a>CMFCAcceleratorKey::SetAccelerator  
 바로 가기 키를 설정 하는 [CMFCAcceleratorKey](../../mfc/reference/cmfcacceleratorkey-class.md) 개체입니다.  
  
```  
void SetAccelerator(LPACCEL lpAccel);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpAccel`  
 바로 가기 키에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드를 사용 하 여에 대 한 바로 가기 키를 설정 하는 `CMFCAcceleratorKey` 를 만들 때 바로 가기 키를 제공 하지 않은 `CMFCAcceleratorKey`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CKeyboardManager 클래스](../../mfc/reference/ckeyboardmanager-class.md)

