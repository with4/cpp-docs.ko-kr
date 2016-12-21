---
title: "C++ 마법사에서 사용하는 JScript 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "마법사 JScript 메서드"
  - "마법사 JScript 메서드, C++ 마법사 만들기"
ms.assetid: f3046c56-cf67-4aaa-919e-8c066bfb6760
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# C++ 마법사에서 사용하는 JScript 함수
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

|||  
|-|-|  
|[AddATLSupportToProject](../ide/addatlsupporttoproject.md)|ATL 지원을 MFC 프로젝트에 추가합니다.|  
|[AddCoclassFromFile](../ide/addcoclassfromfile.md)|coclass가 포함된 템플릿 파일을 렌더링하거나 프로젝트의 .idl 파일에 삽입합니다.|  
|[AddCommonConfig](../ide/addcommonconfig.md)|기본 구성을 프로젝트에 추가합니다.|  
|[AddFilesToProject](../ide/addfilestoproject.md)|Templates.inf 파일의 목록에 있는 모든 파일을 프로젝트에 추가합니다.|  
|[AddInterfaceFromFile](../ide/addinterfacefromfile.md)|인터페이스가 포함된 템플릿 파일을 렌더링하거나 프로젝트의 IDL 파일에 삽입합니다.|  
|[CanAddATLClass](../ide/canaddatlclass.md)|프로젝트가 실행될 코드 마법사와 호환되는지, 즉, ATL 클래스를 사용할 수 있는지 확인하기 위해 마법사에서 호출됩니다.<br /><br /> 마법사는 PREPROCESS\_FUNCTION 매개 변수가 [.vsz 파일\(프로젝트 컨트롤\)](../ide/dot-vsz-file-project-control.md)에 있으면 이 함수를 호출한 다음 [Visual C\+\+ Code Model](http://msdn.microsoft.com/ko-kr/dd6452c2-1054-44a1-b0eb-639a94a1216b)을 사용할 수 있는지 확인합니다.  코드 모델을 사용할 수 없으면 이 함수는 오류를 보고하고 **false**를 반환합니다.|  
|[CanAddClass](../ide/canaddclass.md)|PREPROCESS\_FUNCTION 매개 변수가 프로젝트 컨트롤의 .vsz 파일에 있으면 마법사는 이 함수를 호출합니다.<br /><br /> Visual C\+\+ 코드 모델 개체를 사용할 수 있는지 확인합니다.  코드 모델을 사용할 수 없으면 이 함수는 오류를 보고하고 **false**를 반환합니다.|  
|[CanAddMFCClass](../ide/canaddmfcclass.md)|프로젝트가 실행될 코드 마법사와 호환되는지 확인하기 위해 마법사에서 호출됩니다. MFC 클래스를 사용할 수 있습니다.<br /><br /> 이 마법사는 PREPROCESS\_FUNCTION 매개 변수가 프로젝트 컨트롤의 .vsz 파일에 있으면 이 함수를 호출한 다음 Visual C\+\+ 코드 모델 개체를 사용할 수 있는지 확인합니다.  코드 모델을 사용할 수 없으면 이 함수는 오류를 보고하고 **false**를 반환합니다.|  
|[CanAddNonAttributed](../ide/canaddnonattributed.md)|프로젝트에서 특성을 사용하는 ATL 개체와 특성을 사용하지 않는 ATL 개체를 모두 지원하는지를 나타냅니다.|  
|[CanUseFileName](../ide/canusefilename.md)|파일이 있는지 확인합니다.  파일이 있으면 마법사에서 기존 파일에 추가할 코드를 병합하라는 메시지를 표시합니다.|  
|[ConvertProjectToAttributed](../ide/convertprojecttoattributed.md)|ATL 프로젝트에서 특성을 사용하도록 변환합니다.|  
|[CreateInfFile](../ide/createinffile.md)|Templates.inf 파일을 만듭니다.|  
|[CreateProject](../ide/createproject.md)|C\+\+ 프로젝트를 만듭니다.|  
|[CreateSafeName](../ide/createsafename.md)|C\+\+ 이름을 생성합니다.|  
|[DeleteFile](../ide/deletefile.md)|지정한 파일을 삭제합니다.|  
|[DoesIncludeExist](../ide/doesincludeexist.md)|파일에 `#include` 문을 사용할지를 나타냅니다.|  
|[GetCodeForDllCanUnloadNow](../ide/getcodefordllcanunloadnow.md)|DLL을 언로드하는데 필요한 코드를 검색합니다.|  
|[GetCodeForDllGetClassObject](../ide/getcodefordllgetclassobject.md)|DLL 클래스 개체에 대한 코드를 검색합니다.|  
|[GetCodeForDllRegisterServer](../ide/getcodefordllregisterserver.md)|서버 등록 코드를 검색합니다.|  
|[GetCodeForDllUnregisterServer](../ide/getcodefordllunregisterserver.md)|서버 등록 취소 코드를 검색합니다.|  
|[GetCodeForExitInstance](../ide/getcodeforexitinstance.md)|`ExitInstance`에 사용할 텍스트를 가져오는 도우미 함수입니다.|  
|[GetCodeForInitInstance](../ide/getcodeforinitinstance.md)|[InitInstance](../Topic/CWinApp::InitInstance.md)에 사용할 텍스트를 가져오는 도우미 함수입니다.|  
|[GetExportPragmas](../ide/getexportpragmas.md)|함수를 내보내는 데 사용할 프로그램을 검색합니다.|  
|[GetInterfaceClasses](../ide/getinterfaceclasses.md)|인터페이스와 연관된 `VCCodeClass` 개체를 반환합니다.|  
|[GetInterfaceType](../ide/getinterfacetype.md)|custom, dual, dispinterfaces 및 oleautomation과 같은 인터페이스 형식을 반환합니다.|  
|[GetMaxID](../ide/getmaxid.md)|이 인터페이스의 멤버와 모든 기본 멤버에서 가장 높은 `dispid` 값을 반환합니다.|  
|[GetMemberfunction](../ide/getmemberfunction.md)|지정된 이름을 따라 함수 개체를 반환합니다.|  
|[GetProjectFile](../ide/getprojectfile.md)|.rc, .idl 등과 같이 각 프로젝트별 파일 형식의 이름을 반환합니다.|  
|[GetProjectPath](../ide/getprojectpath.md)|프로젝트의 디렉터리 경로를 반환합니다.|  
|[GetRuntimeErrorDesc](../ide/getruntimeerrordesc.md)|예외 형식에 대한 설명을 반환합니다.|  
|[GetUniqueFileName](../ide/getuniquefilename.md)|고유한 파일 이름을 반환합니다.|  
|[IncludeCodeElementDeclaration](../ide/includecodeelementdeclaration.md)|포함 문을 `strInFile`에 추가합니다. `strCodeElemName`이 구현된 헤더가 프로젝트에 있는 경우 그 헤더도 추가합니다.|  
|[InsertIntoFunction](../ide/insertintofunction.md)|코드를 `InitInstance`에 삽입하기 위해 `AddATLSupportToProject`에서 호출하는 도우미 함수입니다.|  
|[IsATLProject](../ide/isatlproject.md)|프로젝트가 ATL 기반인지를 나타냅니다.|  
|[IsAttributedProject](../ide/isattributedproject.md)|프로젝트에서 특성을 사용하는지를 나타냅니다.|  
|[IsMFCProject](../ide/ismfcproject.md)|프로젝트가 MFC 기반인지를 검사합니다.|  
|[LineBeginsWith](../ide/linebeginswith.md)|특정 문자열이 특정 줄의 맨 앞에 있는지 확인하기 위해 `InsertIntoFunction`에서 호출하는 도우미 함수입니다.|  
|[OffsetToLineNumber](../ide/offsettolinenumber.md)|함수 본문에서 지정한 위치의 줄 번호를 찾습니다.|  
|[OnWizFinish](../ide/onwizfinish.md)|사용자가 **마침**을 클릭할 때 마법사 HTML 스크립트에서 호출됩니다.  마법사 컨트롤의 **Finish** 메서드를 호출합니다.|  
|[RenderAddTemplate](../ide/renderaddtemplate.md)|템플릿 파일을 렌더링합니다. 템플릿 파일을 프로젝트에 추가할 수도 있습니다.|  
|[SetCommonPchSettings](../ide/setcommonpchsettings.md)|미리 컴파일한 헤더를 프로젝트에 사용하기 위해 설정합니다.|  
|[SetErrorInfo](../ide/seterrorinfo.md)|오류 정보를 나타냅니다.|  
|[SetFilters](../ide/setfilters.md)|프로젝트 폴더에 대해 소스 필터, 포함 필터 및 리소스 필터를 추가합니다.|  
|[SetMergeProxySymbol](../ide/setmergeproxysymbol.md)|필요한 경우 \_MERGE\_PROXYSTUB 기호를 추가하기 위해 마법사에서 호출합니다.|  
|[SetNoPchSettings](../ide/setnopchsettings.md)|미리 컴파일한 헤더가 사용되지 않은 경우 프로젝트 구성 속성을 설정합니다.|  
  
## 참고 항목  
 [공용 JScript 함수를 사용하여 C\+\+ 마법사 사용자 지정](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [사용자 지정 마법사 만들기](../ide/creating-a-custom-wizard.md)   
 [마법사 디자인](../ide/designing-a-wizard.md)