---
title: "-디버그 (디버그 정보 생성) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.GenerateDebugInformation
- /debug
dev_langs: C++
helpviewer_keywords:
- DEBUG linker option
- /DEBUG linker option
- -DEBUG linker option
- PDB files
- debugging [C++], debug information files
- generate debug info linker option
- pdb files, generating debug info
- .pdb files, generating debug info
- debugging [C++], linker option
- program databases [C++]
ms.assetid: 1af389ae-3f8b-4d76-a087-1cdf861e9103
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6f9f424a2e71a3094c9e633cbe5779ef5d75fbe9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="debug-generate-debug-info"></a>/DEBUG(디버깅 정보 생성)
```  
/DEBUG[:{FASTLINK|FULL|NONE}]  
```  
  
## <a name="remarks"></a>설명  

**/debug** 옵션은 실행 파일에 대 한 디버깅 정보를 만듭니다.    
  
프로그램 데이터베이스 (PDB) 파일에 디버깅 정보를 저장 하는 링커. 프로그램의 후속 빌드 과정의 PDB를 업데이트합니다.  
  
디버깅을 위해 만든 실행 파일 (.exe 파일 또는 DLL) 이름 및 해당 PDB의 경로 포함 합니다. 디버거는이 포함 된 이름을 읽고 프로그램을 디버깅할 때 PDB를 사용 합니다. 링커는 확장명.pdb 프로그램의 기본 이름을 사용 하 여 프로그램 데이터베이스 이름을 지정 하 고 생성 된 위치 경로 포함 합니다. 이 기본값을 재정의 하려면 설정 [/PDB](../../build/reference/pdb-use-program-database.md) 하 고 다른 파일 이름을 지정 합니다.  

**/debug: fastlink** 옵션 실행 파일을 작성 하는 데 개별 컴파일 제품에 개인 기호 정보를 유지 합니다. 개체 파일 및 전체 복사본을 만드는 대신 실행 파일을 빌드하는 데 사용 되는 라이브러리의 디버그 정보를 인덱싱하는 제한 된 PDB를 생성 합니다. 이 옵션 4 번 빠르게 전체 PDB 생성을 두 개에서 연결할 수 있으며 사용할 수 있는 빌드 제품 있고 로컬로 디버깅 하는 경우에 권장 됩니다. 필요한 빌드 제품 같은 실행 파일 다른 컴퓨터에 배포 되는 경우 사용할 수 없을 때 디버깅을 위해이 제한 된 PDB은 사용할 수 없습니다. 개발자 명령 프롬프트에서이 제한 된 PDB에서 전체 PDB를 생성 하는 mspdbcmf.exe 도구를 사용할 수 있습니다. Visual Studio에서 프로젝트 또는 솔루션에 대 한 전체 PDB를 만들려면 전체 PDB 파일을 생성 하기 위한 프로젝트 또는 빌드 메뉴 항목을 사용 합니다.  
  
**/DEBUG:FULL** 옵션 단일 PDB에 개별 컴파일 제품 (개체 파일 및 라이브러리)에서 모든 개인 기호 정보를 이동 하 고 링크의 가장 시간이 많이 걸리는 일부가 될 수 있습니다. 그러나 다른 빌드 제품이 같은 실행 파일 배포 되는 경우 사용할 수 없는 경우 실행 파일을 디버깅 하려면 전체 PDB은 사용할 수 있습니다.  
  
**/debug: NONE** 옵션 PDB를 생성 하지 않습니다.  
  
지정 하는 경우 **/debug** 링커 기본값으로 추가 옵션 없이 **/DEBUG:FULL** 빌드에 대해 명령줄 및 메이크파일 빌드 릴리스에 대 한 Visual Studio IDE에 디버그 및 릴리스를 모두에 대 한 Visual Studio 2015 및 이전 버전에서 작성합니다. Visual Studio 2017부터, IDE에서 빌드 시스템에서 기본적으로 **/debug: fastlink** 지정 하는 경우는 **/debug** 디버그 빌드에 대 한 옵션입니다. 이전 버전과 호환성을 유지 하기 위해 다른 기본값은 변경 되지 않습니다.  
  
컴파일러의 [C7 호환](../../build/reference/z7-zi-zi-debug-information-format.md) (/ Z7) 옵션을 사용 하면.obj 파일에 디버깅 정보를 유지 합니다. 사용할 수도 있습니다는 [프로그램 데이터베이스](../../build/reference/z7-zi-zi-debug-information-format.md) .obj 파일에 대 한 PDB에 디버깅 정보를 저장 하려면 컴파일러 옵션 (/Zi). 링커는 개체의 pdb를 먼저.obj 파일에 기록 되는 절대 경로에서 찾은 다음 디렉터리에 포함 하는.obj 파일. 개체의 PDB 파일 이름 또는 링커에 위치를 지정할 수 없습니다.  
  
[/ 증분](../../build/reference/incremental-link-incrementally.md) 인 것으로 간주 /DEBUG을 지정 합니다.  
  
/ DEBUG 변경에 대 한 기본값의 [/opt](../../build/reference/opt-optimizations.md) 옵션에서 REF NOREF와 ICF을 NOICF, /opt: ref 또는 /opt: icf 명시적으로 지정 해야 원래 기본값을 사용 하도록 하려는 경우.  
  
만드는.exe 또는.dll 디버그 정보를 포함 하는 것이 불가능 합니다. 디버그 정보는 항상.obj 또는.pdb 파일에 저장 됩니다.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [Visual c + + 프로젝트 속성 설정](../../ide/working-with-project-properties.md)합니다.  
  
2.  클릭는 **링커** 폴더입니다.  
  
3.  클릭는 **디버깅** 속성 페이지.  
  
4.  수정 된 **디버그 정보 생성** 속성을 PDB 생성을 사용 합니다. 이 통해 Visual Studio 2017에서 기본적으로 /debug: fastlink 합니다.  
  
4.  수정 된 **전체 프로그램 데이터베이스 파일 생성** 속성을 모든 증분 빌드에 대 한 전체 PDB 생성을 위한 /DEBUG:FULL을 사용 합니다.  
  
### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
1.  <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.GenerateDebugInformation%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)
