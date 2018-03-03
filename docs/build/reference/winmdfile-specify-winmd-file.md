---
title: "-WINMDFILE (winmd 파일 지정) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.GenerateWindowsMetadataFile
dev_langs:
- C++
ms.assetid: 062b41b3-14d6-432c-a361-fdb66e918931
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 153e5c0bd42b6fdba59e309483f25f09b86fe9fa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="winmdfile-specify-winmd-file"></a>/WINMDFILE(winmd 파일 지정)
생성 되는 Windows 런타임 메타 데이터 (.winmd) 출력 파일에 대 한 파일 이름을 지정는 [/WINMD](../../build/reference/winmd-generate-windows-metadata.md) 링커 옵션입니다.  
  
```  
/WINMDFILE:filename  
```  
  
## <a name="remarks"></a>설명  
 `filename`에 지정된 값을 사용해서 기본 .winmd 파일 이름(`binaryname`.winmd)을 재정의합니다. ".Winmd"를 추가 하지 않으면 확인 `filename`합니다.  여러 값에 나열 되는 **/WINMDFILE** 명령줄 마지막 트랜잭션이 우선 합니다.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  선택 된 **링커** 폴더입니다.  
  
3.  선택 된 **Windows 메타 데이터** 속성 페이지.  
  
4.  에 **Windows 메타 데이터 파일** 상자 파일 위치를 입력 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [/WINMD (Windows 메타 데이터 생성)](../../build/reference/winmd-generate-windows-metadata.md)   
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)