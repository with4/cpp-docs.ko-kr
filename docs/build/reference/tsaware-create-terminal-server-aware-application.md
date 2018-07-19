---
title: -TSAWARE (터미널 서버 인식 응용 프로그램 만들기) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /tsaware
- VC.Project.VCLinkerTool.TerminalServerAware
dev_langs:
- C++
helpviewer_keywords:
- Terminal Server
- /TSAWARE linker option
- Terminal Server, Terminal Server-aware applications
- -TSAWARE linker option
- TSAWARE linker option
ms.assetid: fe1c1846-de5b-4839-b562-93fbfe36cd29
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e386c9024ea7736adb2766488c1c51c80ff7177b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32379135"
---
# <a name="tsaware-create-terminal-server-aware-application"></a>/TSAWARE(터미널 서버 인식 응용 프로그램 만들기)
```  
/TSAWARE[:NO]  
```  
  
## <a name="remarks"></a>설명  
 /TSAWARE 옵션은 프로그램 이미지의 선택적 헤더에 있는 IMAGE_OPTIONAL_HEADER DllCharacteristics 필드에 플래그를 설정합니다. 이 플래그를 설정하면 터미널 서버가 응용 프로그램에서 특정 변경 작업을 수행할 수 없습니다.  
  
 터미널 서버 인식 (레거시 응용 프로그램이 라고도 함) 응용 프로그램이 없는 경우 터미널 서버에서는 레거시 응용 프로그램이 다중 사용자 환경에서 제대로 작동 하도록 특정 사항을 수정 합니다. 예를 들어 터미널 서버는 각 사용자가 시스템의 Windows 디렉터리를 가져오는 대신 Windows 폴더에는 가상 Windows 폴더가 만들어집니다. 그러면 사용자가 액세스할 자신의 INI 파일에 있습니다. 또한 터미널 서버에서는 레거시 응용 프로그램에 대 한 레지스트리 약간 수정 합니다. 이러한 수정 사항은 터미널 서버에서 레거시 응용 프로그램의 로드 속도가 느린 합니다.  
  
 터미널 서버 인식 응용 프로그램을 사용 하는 경우 그 해야 INI 파일에 의존 아니고에 쓰기는 **HKEY_CURRENT_USER** 설치 하는 동안 레지스트리 합니다.  
  
 /TSAWARE를 사용 하 고 INI 파일에 계속 사용 하 여 응용 프로그램을 파일 시스템의 모든 사용자가 공유 됩니다. 허용 되는 응용 프로그램 /TSAWARE;에 링크할 수 있습니다. 그렇지 않으면 /tsaware: no를 사용 해야 합니다.  
  
 /TSAWARE 옵션은 Windows 및 콘솔 응용 프로그램에 대해 기본적으로 활성화 됩니다. 참조 [/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md) 및 [/VERSION](../../build/reference/version-version-information.md) 정보에 대 한 합니다.  
  
 /TSAWARE는 드라이버, Vxd, 또는 Dll에 대해 올바르지 않습니다.  
  
 응용 프로그램에 /TSAWARE, DUMPBIN 링크 된 경우 [/HEADERS](../../build/reference/headers.md) 그 결과 정보가 표시 됩니다.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [Visual c + + 프로젝트 속성 설정](../../ide/working-with-project-properties.md)합니다.  
  
2.  클릭는 **링커** 폴더입니다.  
  
3.  클릭는 **시스템** 속성 페이지.  
  
4.  수정 된 **터미널 서버** 속성입니다.  
  
### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TerminalServerAware%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)   
 [사용자 관련 정보를 저장합니다.](http://msdn.microsoft.com/library/aa383452)   
 [터미널 서비스 환경에서 레거시 응용 프로그램](https://msdn.microsoft.com/en-us/library/aa382957.aspx)