---
title: -PDB (프로그램 데이터베이스 사용) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /pdb
- VC.Project.VCLinkerTool.ProgramDatabaseFile
dev_langs:
- C++
helpviewer_keywords:
- -PDB linker option
- /PDB linker option
- PDB linker option
- PDB files, creating
- .pdb files, creating
ms.assetid: d23db0ce-10cb-427a-bc60-d6b2a852723d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 776d23c0c0c7ce392b1ff0d7a989c3c5503129b8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32376001"
---
# <a name="pdb-use-program-database"></a>/PDB(프로그램 데이터베이스 사용)
```  
/PDB:filename  
```  
  
## <a name="remarks"></a>설명  
 다음은 각 문자에 대한 설명입니다.  
  
 *filename*  
 링커가 만드는 프로그램 데이터베이스 (PDB)에 대 한 사용자 지정 이름입니다. 기본 이름을 대체합니다.  
  
## <a name="remarks"></a>설명  
 기본적으로 때 [/debug](../../build/reference/debug-generate-debug-info.md) 지정, 링커가 디버깅 정보를 보유 하는 프로그램 데이터베이스 (PDB)를 만듭니다. PDB에 대 한 기본 파일 이름을 확장명.pdb 프로그램의 기본 이름입니다.  
  
 /PDB을 사용 하 여:*filename* PDB 파일의 이름을 지정할 수 있습니다. /DEBUG을 지정 하지 않으면 /PDB 옵션은 무시 됩니다.  
  
 PDB 파일 최대 2GB까지 될 수 있습니다.  
  
 자세한 내용은 참조 [링커 입력 파일로.pdb 파일](../../build/reference/dot-pdb-files-as-linker-input.md)합니다.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [Visual c + + 프로젝트 속성 설정](../../ide/working-with-project-properties.md)합니다.  
  
2.  클릭는 **링커** 폴더입니다.  
  
3.  클릭는 **디버그** 속성 페이지.  
  
4.  수정 된 **프로그램 데이터베이스 파일 생성** 속성입니다.  
  
### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ProgramDatabaseFile%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)