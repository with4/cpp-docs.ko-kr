---
title: "클래스 팩터리 및 라이선스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros.classes
dev_langs:
- C++
helpviewer_keywords:
- class factories, and licensing
ms.assetid: 53c4856a-4062-46db-9f69-dd4339f746b3
caps.latest.revision: 13
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
ms.sourcegitcommit: 17a158366f94d27b7a46917282425d652e6b9042
ms.openlocfilehash: a8ef7ba19d2337e4e50f34d7cdd528024a1d90aa
ms.lasthandoff: 02/24/2017

---
# <a name="class-factories-and-licensing"></a>클래스 팩터리 및 라이선스
OLE 컨트롤의 인스턴스를 만들려면 컨테이너 응용 프로그램 컨트롤의 클래스 팩터리의 멤버 함수를 호출 합니다. 컨트롤의 실제 OLE 개체 이기 때문에 클래스 팩토리는 컨트롤의 인스턴스를 만들기 위한 담당 합니다. 모든 OLE 컨트롤 클래스는 클래스 팩터리가 있어야 합니다.  
  
 OLE 컨트롤의 또 다른 중요 한 특징은 라이선스를 적용할 수 있습니다. 컨트롤을 사용 하면 컨트롤 프로젝트를 만드는 동안 라이선스를 통합할 수 있습니다. 컨트롤 라이선스에 대 한 자세한 내용은 문서를 참조 하십시오. [ActiveX 컨트롤: ActiveX 컨트롤 라이선스](../../mfc/mfc-activex-controls-licensing-an-activex-control.md)합니다.  
  
 다음 표에 몇 가지 매크로 함수를 선언 하 고 컨트롤의 클래스 팩터리를 구현 하는 데 사용 하 여 컨트롤의 라이선스입니다.  
  
### <a name="class-factories-and-licensing"></a>클래스 팩터리 및 라이선스  
  
|||  
|-|-|  
|[DECLARE_OLECREATE_EX](#declare_olecreate_ex)|OLE 컨트롤 또는 속성 페이지에 대 한 클래스 팩터리를 선언합니다.|  
|[IMPLEMENT_OLECREATE_EX](#implement_olecreate_ex)|컨트롤의 구현 `GetClassID` 함수 및 클래스 팩터리 인스턴스를 선언 합니다.|  
|[BEGIN_OLEFACTORY](#begin_olefactory)|모든 라이선스 함수 선언의 시작합니다.|  
|[END_OLEFACTORY](#end_olefactory)|모든 라이선스 함수의 선언이 종료 됩니다.|  
|[AfxVerifyLicFile](#afxverifylicfile)|컨트롤이 특정 컴퓨터에서 사용 하도록 허가 되어 있는지 여부를 확인 합니다.|  
  
##  <a name="a-namedeclareolecreateexa--declareolecreateex"></a><a name="declare_olecreate_ex"></a>DECLARE_OLECREATE_EX  
 클래스 팩터리를 선언 및 `GetClassID` 컨트롤 클래스의 멤버 함수입니다.  
  
```   
DECLARE_OLECREATE_EX(class_name)   
```  
  
### <a name="parameters"></a>매개 변수  
 *눈여겨 보십시오*  
 컨트롤 클래스의 이름입니다.  
  
### <a name="remarks"></a>주의  
 이 매크로 사용 하 여 라이선스를 지원 하지 않는 컨트롤에 대 한 컨트롤 클래스 헤더 파일에 있습니다.  
  
 이 매크로 다음 코드 예제와 같은 용도로 사용 되는 참고:  
  
 [!code-cpp[NVC_MFCAxCtl #&14;](../../mfc/reference/codesnippet/cpp/class-factories-and-licensing_1.h)]  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxctl.h  
  
##  <a name="a-nameimplementolecreateexa--implementolecreateex"></a><a name="implement_olecreate_ex"></a>IMPLEMENT_OLECREATE_EX  
 컨트롤의 클래스 팩터리를 구현 하 고 [GetClassID](../../mfc/reference/colecontrol-class.md#getclassid) 컨트롤 클래스의 멤버 함수입니다.  
  
```   
IMPLEMENT_OLECREATE_EX(
   class_name,   
    external_name,    
    l,   
    w1,   
    w2,   
    b1,   
    b2,   
    b3,   
    b4,   
    b5,   
    b6,   
    b7,
    b8)   
```  
  
### <a name="parameters"></a>매개 변수  
 *눈여겨 보십시오*  
 컨트롤 속성 페이지 클래스의 이름입니다.  
  
 *external_name*  
 응용 프로그램에 노출 되는 개체 이름입니다.  
  
 *l, w1, w2, b1, b&2;, b&3;, b&4;, b&5;, b&6;, b&7;, b&8;*  
 구성 요소는 클래스의 **CLSID**합니다. 이러한 매개 변수에 대 한 자세한 내용은 설명 부분을 참조 하십시오. [IMPLEMENT_OLECREATE](run-time-object-model-services.md#implement_olecreate)합니다.  
  
### <a name="remarks"></a>주의  
 이 매크로 사용 하는 컨트롤 클래스는 구현 파일에 표시 되어야는 `DECLARE_OLECREATE_EX` 매크로 또는 `BEGIN_OLEFACTORY` 및 `END_OLEFACTORY` 매크로입니다. 외부 이름에는 다른 응용 프로그램에 노출 되는 OLE 컨트롤의 식별자입니다. 이 컨트롤 클래스의 개체를 요청 하는 데이 이름을 사용 하는 컨테이너입니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxctl.h  
  
##  <a name="a-namebeginolefactorya--beginolefactory"></a><a name="begin_olefactory"></a>BEGIN_OLEFACTORY  
 사용자 컨트롤 클래스의 헤더 파일에서 클래스 팩터리의 선언을 시작합니다.  
  
``` 
BEGIN_OLEFACTORY(class_name)  
```  
  
### <a name="parameters"></a>매개 변수  
 *눈여겨 보십시오*  
 이 해당 클래스 팩터리 컨트롤 클래스의 이름을 지정 합니다.  
  
### <a name="remarks"></a>주의  
 클래스 팩터리의 라이선스 함수 선언 후 즉시 시작 해야 `BEGIN_OLEFACTORY`합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxctl.h  
  
##  <a name="a-nameendolefactorya--endolefactory"></a><a name="end_olefactory"></a>END_OLEFACTORY  
 컨트롤의 클래스 팩터리의 선언을 종료 합니다.  
  
```  
END_OLEFACTORY(class_name)   
```  
  
### <a name="parameters"></a>매개 변수  
 *눈여겨 보십시오*  
 이 해당 클래스 팩터리 컨트롤 클래스의 이름입니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxctl.h  
  
##  <a name="a-nameafxverifylicfilea--afxverifylicfile"></a><a name="afxverifylicfile"></a>AfxVerifyLicFile  
 호출 하 여 라이선스 파일의 이름이 있는지 확인 하려면이 함수를 `pszLicFileName` OLE 컨트롤에 대 한 유효 합니다.  
  
```   
BOOL AFXAPI AfxVerifyLicFile(
    HINSTANCE  hInstance,  
    LPCTSTR  pszLicFileName,  
    LPOLESTR  pszLicFileContents,  
    UINT cch = -1); 
```  
  
### <a name="parameters"></a>매개 변수  
 `hInstance`  
 사용이 허가 된 컨트롤과 연결 된 DLL의 인스턴스 핸들입니다.  
  
 `pszLicFileName`  
 라이선스 파일 이름을 포함 하는 문자를 null로 끝나는 문자열을 가리킵니다.  
  
 `pszLicFileContents`  
 라이선스 파일의 시작 부분에서 찾을 시퀀스와 일치 해야 하는 바이트 시퀀스를 가리킵니다.  
  
 `cch`  
 문자 수가 `pszLicFileContents`합니다.  
  
### <a name="return-value"></a>반환 값  
 라이선스 파일이 있으며에서 문자 시퀀스를 시작 하는 경우 0이 아닌 `pszLicFileContents`그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 경우 `cch` â €는 "1,이 함수를 사용 합니다.  
  
 [!code-cpp[NVC_MFC_Utilities #&36;](../../mfc/codesnippet/cpp/class-factories-and-licensing_2.cpp)]  

### <a name="requirements"></a>요구 사항  
  **헤더** afxctl.h  

## <a name="see-also"></a>참고 항목  
 [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)

