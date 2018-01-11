---
title: "클래스 팩터리 및 라이선스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.mfc.macros.classes
dev_langs: C++
helpviewer_keywords: class factories [MFC], and licensing
ms.assetid: 53c4856a-4062-46db-9f69-dd4339f746b3
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 79710cb1fa67ec8315fe287364126f88b4b498d7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="class-factories-and-licensing"></a>클래스 팩터리 및 라이선스
OLE 컨트롤의 인스턴스를 만들려면 컨테이너 응용 프로그램의 컨트롤의 클래스 팩터리 멤버 함수를 호출 합니다. 컨트롤은 실제 OLE 개체, 클래스 팩터리는 컨트롤의 인스턴스를 만들기 위한 해야 합니다. 모든 OLE 컨트롤 클래스는 클래스 팩터리를 가져야 합니다.  
  
 OLE 컨트롤의 또 다른 중요 한 특징은 라이선스를 적용할 수 있습니다. 컨트롤을 사용 하면 컨트롤 프로젝트를 만드는 동안 라이선스를 통합할 수 있습니다. 컨트롤 라이선스에 대 한 자세한 내용은 문서 참조 [ActiveX 컨트롤: ActiveX 컨트롤 라이선스](../../mfc/mfc-activex-controls-licensing-an-activex-control.md)합니다.  
  
 다음 표에서 다양 한 매크로 및 선언 하 고 컨트롤의 클래스 팩터리를 구현 하는 데 사용 되는 함수를 나열 하 고 컨트롤의 라이선스를 합니다.  
  
### <a name="class-factories-and-licensing"></a>클래스 팩터리 및 라이선스  
  
|||  
|-|-|  
|[DECLARE_OLECREATE_EX](#declare_olecreate_ex)|OLE 컨트롤 또는 속성 페이지에 대 한 클래스 팩터리를 선언합니다.|  
|[IMPLEMENT_OLECREATE_EX](#implement_olecreate_ex)|컨트롤의 구현 `GetClassID` 작동 하 고 클래스 팩터리의 인스턴스를 선언 합니다.|  
|[BEGIN_OLEFACTORY](#begin_olefactory)|모든 라이선스 함수 선언을 시작합니다.|  
|[END_OLEFACTORY](#end_olefactory)|모든 라이선스 함수의 선언을 종료 됩니다.|  
|[AfxVerifyLicFile](#afxverifylicfile)|컨트롤이 특정 컴퓨터에서 사용 하도록 허가 되어 있는지 여부를 확인 합니다.|  
  
##  <a name="declare_olecreate_ex"></a>DECLARE_OLECREATE_EX  
 클래스 팩터리를 선언 및 `GetClassID` 컨트롤 클래스의 멤버 함수입니다.  
  
```   
DECLARE_OLECREATE_EX(class_name)   
```  
  
### <a name="parameters"></a>매개 변수  
 *class_name*  
 컨트롤 클래스의 이름입니다.  
  
### <a name="remarks"></a>설명  
 이 매크로 사용 하 여 라이선스를 지원 하지 않는 컨트롤에 대 한 컨트롤 클래스 헤더 파일에 있습니다.  
  
 이 매크로 다음 코드 샘플으로 동일한 용도로 사용 하는 참고:  
  
 [!code-cpp[NVC_MFCAxCtl#14](../../mfc/reference/codesnippet/cpp/class-factories-and-licensing_1.h)]  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxctl.h  
  
##  <a name="implement_olecreate_ex"></a>IMPLEMENT_OLECREATE_EX  
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
 *class_name*  
 컨트롤 속성 페이지 클래스의 이름입니다.  
  
 *external_name*  
 응용 프로그램에 노출 하는 개체 이름입니다.  
  
 *l, w1, w2, b 1, b 2, b 3, b 4, b 5, b 6, b 7, b 8*  
 클래스의의 구성 요소 **CLSID**합니다. 이러한 매개 변수에 대 한 자세한 내용은 설명 부분을 참조 하십시오. [IMPLEMENT_OLECREATE](run-time-object-model-services.md#implement_olecreate)합니다.  
  
### <a name="remarks"></a>설명  
 이 매크로 사용 하는 모든 컨트롤 클래스에 대 한 구현 파일에 나타나야 합니다는 `DECLARE_OLECREATE_EX` 매크로 또는 `BEGIN_OLEFACTORY` 및 `END_OLEFACTORY` 매크로입니다. 외부 이름에는 다른 응용 프로그램에 노출 되는 OLE 컨트롤의 식별자입니다. 컨테이너에는이 컨트롤 클래스의 개체를 요청 하려면이 이름을 사용 합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxctl.h  
  
##  <a name="begin_olefactory"></a>BEGIN_OLEFACTORY  
 컨트롤 클래스의 헤더 파일에서 클래스 팩터리의 선언을 시작합니다.  
  
``` 
BEGIN_OLEFACTORY(class_name)  
```  
  
### <a name="parameters"></a>매개 변수  
 *class_name*  
 이 해당 클래스 팩터리 컨트롤 클래스의 이름을 지정 합니다.  
  
### <a name="remarks"></a>설명  
 클래스 팩터리 함수를 라이선스의 선언 후 즉시 시작 되어야 `BEGIN_OLEFACTORY`합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxctl.h  
  
##  <a name="end_olefactory"></a>END_OLEFACTORY  
 컨트롤의 클래스 팩터리의 선언을 종료합니다.  
  
```  
END_OLEFACTORY(class_name)   
```  
  
### <a name="parameters"></a>매개 변수  
 *class_name*  
 이 해당 클래스 팩터리 컨트롤 클래스의 이름입니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxctl.h  
  
##  <a name="afxverifylicfile"></a>AfxVerifyLicFile  
 이 함수를 확인 하 여 라이선스 파일 라는 호출 `pszLicFileName` OLE 컨트롤에 대 한 유효 합니다.  
  
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
 라이선스 파일의 시작 부분에 있는 시퀀스와 일치 해야 하는 바이트 시퀀스를 가리킵니다.  
  
 `cch`  
 에 있는 문자의 수 `pszLicFileContents`합니다.  
  
### <a name="return-value"></a>반환 값  
 라이선스 파일이 있고에서 문자 시퀀스를 시작 하는 경우 0이 아닌 `pszLicFileContents`그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 경우 `cch` -1 이면이 함수를 사용 합니다.  
  
 [!code-cpp[NVC_MFC_Utilities#36](../../mfc/codesnippet/cpp/class-factories-and-licensing_2.cpp)]  

### <a name="requirements"></a>요구 사항  
  **헤더** afxctl.h  

## <a name="see-also"></a>참고 항목  
 [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)
