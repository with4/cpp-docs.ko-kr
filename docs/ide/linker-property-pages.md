---
title: 링커 속성 페이지 | Microsoft Docs
ms.custom: ''
ms.date: 11/21/2017
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.VCLinkerTool.RegisterOutput
- VC.Project.VCLinkerTool.OVERWRITEImportLibrary
- VC.Project.VCLinkerTool.UseLibraryDependencyInputs
- VC.Project.VCLinkerTool.LinkLibraryDependencies
dev_langs:
- C++
helpviewer_keywords:
- per-user redirection
- Linker property pages
ms.assetid: 7e7671e5-a35a-4e67-9bdb-661d75c4d11e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2cec232bb4e4f2f6ac1ab9af703b368eec0ba5dd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="linker-property-pages"></a>링커 속성 페이지

이 항목에서는 다음과 같은 속성에 설명 된 **일반** 링커 속성 페이지. 이 페이지의 Linux 버전에 대 한 참조 [링커 속성 (Linux c + +)](../linux/prop-pages/linker-linux.md)합니다.

## <a name="general-page-properties"></a>일반 페이지 속성

### <a name="ignore-import-library"></a>가져오기 라이브러리 무시

이 속성을 사용 하면 링커에서에 종속 프로젝트에 있는이 빌드에서 생성 된.lib 출력을 연결 하지 않습니다. 이 통해 프로젝트 시스템을 빌드할 때 표시 되는.lib 파일을 생성 하지 않는.dll 파일을 처리 합니다. DLL을 생성 하는 다른 프로젝트에 종속 되는 프로젝트를 프로젝트 시스템이 자동으로 자식 프로젝트에서 생성 한.lib 파일을 연결 합니다. COM Dll 또는 리소스 전용 Dll; 생성 된 프로젝트에 필요 하지 않을 수 있습니다이 이러한 Dll에 있는 의미 있는 내보내기가 없습니다. DLL 내보내기가 없는 경우 링커는.lib 파일을 생성 하지 않습니다. 내보내기.lib 파일이 된 디스크, 하는 경우 프로젝트 시스템 (누락 된) DLL이를 사용 하 여 링크를 사용 하면 링커에서 링크 실패 합니다. 사용 하 여는 **가져오기 라이브러리 무시** 이 문제를 해결 하는 속성입니다. 로 설정 하면 **예**, 프로젝트 시스템에서 해당.lib 파일의 유무를 무시 하 고 존재 하지 않는.lib 파일에 링크 되지 않도록이 프로젝트에 종속 된 모든 프로젝트가 발생 합니다.

프로그래밍 방식으로 이 속성에 액세스하려면 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreImportLibrary%2A>을 참조하세요.

### <a name="register-output"></a>출력 등록

실행 `regsvr32.exe /s $(TargetPath)` 빌드 출력에는.dll 프로젝트 에서만 유효 합니다. .Exe 프로젝트의 경우이 속성은 무시 됩니다. .Exe 출력을 등록 하려면 항상 등록 된.exe 파일에 대 한 필요한 것은 사용자 지정 등록 작업을 수행 하는 구성에 사후 빌드 이벤트를 설정 합니다.

프로그래밍 방식으로 이 속성에 액세스하려면 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.RegisterOutput%2A>을 참조하세요.

### <a name="per-user-redirection"></a>사용자별 리디렉션

일반적으로 Visual Studio에서 등록 HKEY_CLASSES_ROOT (HKCR)에서 수행 하지 않았습니다. Windows Vista 및 이후 운영 체제와 HKCR에 액세스 하려면 Visual Studio을 승격 된 모드에서 실행 해야 있습니다. 개발자는 항상 원하지 않는 관리자 모드에서 실행 하지만 등록 에서도 계속 작동 해야 합니다. 사용자 단위 리디렉션을 사용 하면이 모드에서 실행 하지 않고도 등록할 수 있습니다.

사용자 단위 리디렉션을 HKEY 리디렉션할 수 HKCR에 한 쓰기가 강제로\_현재\_사용자 (HKCU). 사용자 단위 리디렉션을 해제 하는 경우 발생할 수 있습니다 [프로젝트 빌드 오류 PRJ0050](../error-messages/tool-errors/project-build-error-prj0050.md) HKCR에는 프로그램을 사용 하는 경우.

### <a name="link-library-dependencies"></a>라이브러리 종속성 링크

한.lib 파일인 종속 프로젝트에서 생성 되는 링크 여부를 지정 합니다. 일반적으로,.lib 파일에 연결 하려는 하지만 특정 Dll에 대 한 대/소문자 아닐 수 있습니다.

예를 들어 상대 경로 파일 이름을 제공 하 여.obj 파일을 지정할 수도 있습니다 "... \\.. \MyLibProject\MyObjFile.obj "입니다. .Obj 파일의 소스 코드에 경우 # pch.obj 파일은 MyObjFile.obj와 동일한 폴더에 있으며 pch.obj 추가 종속성으로 추가 해야 합니다는 미리 컴파일된 헤더 예: pch.h includes 합니다.

### <a name="use-library-dependency-inputs"></a>라이브러리 종속성 입력 사용

대규모 프로젝트에서.lib 파일을 생성 하는 종속 프로젝트 증분 링크는 사용할 수 없습니다. .Lib 파일을 생성 하는 여러 종속 프로젝트에 있는 경우 응용 프로그램 빌드 오래를 걸릴 수 있습니다. 이 속성이로 설정 된 경우 **예**,.lib.obj 파일에 프로젝트 시스템이 연결 증분 링크를 활성화 하는 종속 프로젝트에서 생성 합니다.

액세스 하는 방법에 대 한 내용은 **일반** 링커 속성 페이지 참조 [프로젝트 속성 작업](../ide/working-with-project-properties.md)합니다.

## <a name="see-also"></a>참고자료

[옵션 대화 상자, 프로젝트 및 솔루션, VC++ 프로젝트 설정](/visualstudio/ide/reference/vcpp-project-settings-projects-and-solutions-options-dialog-box)  
[속성 페이지](../ide/property-pages-visual-cpp.md)  