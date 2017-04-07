---
title: "CMFCPropertyGridFileProperty 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCPropertyGridFileProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFileProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFileProperty::CMFCPropertyGridFileProperty
dev_langs:
- C++
helpviewer_keywords:
- CMFCPropertyGridFileProperty class
- CMFCPropertyGridFileProperty::OnClickButton method
ms.assetid: 2bb8b8b4-47fc-4798-bd5e-dc8ea0b4cd9d
caps.latest.revision: 25
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
ms.openlocfilehash: 56e9d258f5d608b03497632bef84cf73611f2e9a
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcpropertygridfileproperty-class"></a>CMFCPropertyGridFileProperty 클래스
`CMFCPropertyGridFileProperty` 클래스 파일 선택 대화 상자를 여는 속성 목록 컨트롤 항목을 지원 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMFCPropertyGridFileProperty : public CMFCPropertyGridProperty  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCPropertyGridFileProperty::CMFCPropertyGridFileProperty](#cmfcpropertygridfileproperty)|`CMFCPropertyGridFileProperty` 개체를 생성합니다.|  
|`CMFCPropertyGridFileProperty::~CMFCPropertyGridFileProperty`|소멸자|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|`CMFCPropertyGridFileProperty::GetThisClass`|에 대 한 포인터를 가져오는 데 프레임 워크에 의해는 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 이 클래스 형식으로 연결 된 개체입니다.|  
|`CMFCPropertyGridFileProperty::OnClickButton`|(재정의 [CMFCPropertyGridProperty::OnClickButton](../../mfc/reference/cmfcpropertygridproperty-class.md#onclickbutton).)|  
  
### <a name="remarks"></a>주의  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)  
  
 [CMFCPropertyGridFileProperty](../../mfc/reference/cmfcpropertygridfileproperty-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxpropertygridctrl.h  
  
##  <a name="cmfcpropertygridfileproperty"></a>CMFCPropertyGridFileProperty::CMFCPropertyGridFileProperty  
 `CMFCPropertyGridFileProperty` 개체를 생성합니다.  
  
```  
CMFCPropertyGridFileProperty(
    const CString& strName,  
    BOOL bOpenFileDialog,  
    const CString& strFileName,  
    LPCTSTR lpszDefExt=NULL,  
    DWORD dwFlags=OFN_HIDEREADONLY|OFN_OVERWRITEPROMPT,  
    LPCTSTR lpszFilter=NULL,  
    LPCTSTR lpszDescr=NULL,  
    DWORD_PTR dwData=0);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `strName`  
 속성 이름입니다.  
  
 [in] `bOpenFileDialog`  
 `TRUE`열려는 프로그램 **파일 열기** 대화 상자입니다. `FALSE` 열려는 **파일 저장** 대화 상자입니다.  
  
 [in] `strFileName`  
 초기 파일 이름입니다.  
  
 [in] `lpszDefExt`  
 하나 이상의 파일 이름 확장명의 문자열입니다. 기본값은 `NULL`입니다.  
  
 [in] `dwFlags`  
 대화 상자 플래그입니다. 기본값은 `OFN_HIDEREADONLY`와 `OFN_OVERWRITEPROMPT`의 비트 조합(OR)입니다.  
  
 [in] `lpszFilter`  
 하나 이상의 파일 필터의 문자열입니다. 기본값은 `NULL`입니다.  
  
 [in] `lpszDescr`  
 속성 항목 설명입니다. 기본값은 `NULL`입니다.  
  
 [in] `dwData`  
 속성 항목과 연결된 응용 프로그램별 데이터입니다. 예를 들어 32비트 정수 또는 다른 데이터에 대한 포인터입니다. 기본값은 0입니다.  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
 사용 가능한 플래그의 전체 목록은 참조 하십시오. [OPENFILENAME 구조](https://msdn.microsoft.com/library/ms646839.aspx)합니다.  
  
### <a name="example"></a>예제  
 다음 예제에서는 `CMFCPropertyGridFileProperty` 클래스의 생성자를 사용하여 개체를 만드는 방법을 보여 줍니다. 이 예제는의 일부는 [Visual Studio 데모 샘플](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo #&22;](../../mfc/codesnippet/cpp/cmfcpropertygridfileproperty-class_1.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCPropertyGridCtrl 클래스](../../mfc/reference/cmfcpropertygridctrl-class.md)   
 [CMFCPropertyGridProperty 클래스](../../mfc/reference/cmfcpropertygridproperty-class.md)

