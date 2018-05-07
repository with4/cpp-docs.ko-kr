---
title: CMFCAcceleratorKey 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCAcceleratorKey
- AFXACCELERATORKEY/CMFCAcceleratorKey
- AFXACCELERATORKEY/CMFCAcceleratorKey::CMFCAcceleratorKey
- AFXACCELERATORKEY/CMFCAcceleratorKey::Format
- AFXACCELERATORKEY/CMFCAcceleratorKey::SetAccelerator
dev_langs:
- C++
helpviewer_keywords:
- CMFCAcceleratorKey [MFC], CMFCAcceleratorKey
- CMFCAcceleratorKey [MFC], Format
- CMFCAcceleratorKey [MFC], SetAccelerator
ms.assetid: d140fbf7-23db-45ea-a63e-414a5ec7b3d5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e6ca49fd2696a8fc5a488962f1f13ead1d861c20
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
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
|[CMFCAcceleratorKey::Format](#format)|가속 구조 시각적 표현으로 변환합니다.|  
|[CMFCAcceleratorKey::SetAccelerator](#setaccelerator)|에 대 한 바로 가기 키 설정의 `CMFCAcceleratorKey` 개체입니다.|  
  
## <a name="remarks"></a>설명  
 액셀러레이터 키가 바로 가기 키 라고도 합니다. 사용자가 입력 하는 바로 가기 키를 표시 하려는 경우는 [CMFCAcceleratorKeyAssignCtrl 클래스](../../mfc/reference/cmfcacceleratorkeyassignctrl-class.md) 맵 바로 가기 키, Alt + Shift + S, 예: "Alt + Shift + S" 등의 사용자 지정 텍스트 서식입니다. 각 `CMFCAcceleratorKey` 개체는 단일 바로 가기 키를 텍스트 형식으로 매핑합니다.  
  
 바로 가기 키 및 액셀러레이터 키 테이블을 사용 하는 방법에 대 한 자세한 내용은 참조 [CKeyboardManager 클래스](../../mfc/reference/ckeyboardmanager-class.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 생성 하는 방법을 `CMFCAcceleratorKey` 개체와 사용 하는 방법의 `Format` 메서드.  
  
 [!code-cpp[NVC_MFC_RibbonApp#30](../../mfc/reference/codesnippet/cpp/cmfcacceleratorkey-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMFCAcceleratorKey`   
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxacceleratorkey.h  
  
##  <a name="cmfcacceleratorkey"></a>  CMFCAcceleratorKey::CMFCAcceleratorKey  
 생성 된 [CMFCAcceleratorKey](../../mfc/reference/cmfcacceleratorkey-class.md) 개체입니다.  
  
```  
CMFCAcceleratorKey();  
CMFCAcceleratorKey(LPACCEL lpAccel);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpAccel`  
 바로 가기 키에 대 한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 만들 때 바로 가기 키를 제공 하지 않으면는 `CMFCAccleratorKey`를 사용 하 여는 [CMFCAcceleratorKey::SetAccelerator](#setaccelerator) 된 바로 가기 키를 연결 하는 방법이 프로그램 `CMFCAcceleratorKey` 개체입니다.  
  
##  <a name="format"></a>  CMFCAcceleratorKey::Format  
 가속 구조를 연결 된 문자열 값으로 변환합니다.  
  
```  
void Format(CString& str) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [out] `str`  
 에 대 한 참조는 `CString` 메서드 번역 된 바로 가기 키를 기록 하는 위치 개체입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 관련 된 바로 가기 키의 문자열 형식을 검색합니다. 문자열 형식을 설정할 수 있습니다는 [CMFCAcceleratorKey](../../mfc/reference/cmfcacceleratorkey-class.md) 개체 생성자 또는 메서드 중 하나를 사용 하 여 [CMFCAcceleratorKey::SetAccelerator](#setaccelerator)합니다.  
  
##  <a name="setaccelerator"></a>  CMFCAcceleratorKey::SetAccelerator  
 에 대 한 바로 가기 키 설정의 [CMFCAcceleratorKey](../../mfc/reference/cmfcacceleratorkey-class.md) 개체입니다.  
  
```  
void SetAccelerator(LPACCEL lpAccel);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpAccel`  
 바로 가기 키에 대 한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드를 사용 하 여에 대 한 바로 가기 키를 설정 하는 `CMFCAcceleratorKey` 만든 때 바로 가기 키를 제공 하지 않은 `CMFCAcceleratorKey`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CKeyboardManager 클래스](../../mfc/reference/ckeyboardmanager-class.md)
