---
title: "-스텁 (MS-DOS 스텁 파일 이름) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /stub
- VC.Project.VCLinkerTool.DosStub
dev_langs: C++
helpviewer_keywords:
- Win32 [C++], attaching MS-DOS stub program
- STUB linker option
- MS-DOS stub file name linker option
- /STUB linker option
- Windows API [C++], attaching MS-DOS stub program
- -STUB linker option
ms.assetid: 65221ffe-4f9a-4a14-ac69-3cfb79b40b5f
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2bb7d1b9f56e7cea5d476d5ece6bdfab50fbe7a9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="stub-ms-dos-stub-file-name"></a>/STUB(MS-DOS 스텁 파일 이름)
```  
/STUB:filename  
```  
  
## <a name="remarks"></a>설명  
 다음은 각 문자에 대한 설명입니다.  
  
 *filename*  
 MS-DOS 응용 프로그램입니다.  
  
## <a name="remarks"></a>설명  
 /STUB 옵션은 MS-DOS 스텁 프로그램을 Win32 프로그램에 연결합니다.  
  
 스텁 프로그램 파일 MS-DOS에서 실행 되는 경우 호출 됩니다. 일반적으로 적절 한 메시지; 표시 그러나 모든 유효한 MS-DOS 응용 프로그램 스텁 프로그램을 수 있습니다.  
  
 지정 된 *filename* 스텁 프로그램 명령줄에 콜론 (:) 다음에 대 한 합니다. 링커 검사 *filename* 파일 실행 파일이 없는 경우 오류 메시지를 표시 하 고 있습니다. 이 프로그램은.exe 파일; 이어야 합니다. .com 파일 스텁 프로그램에 대해 올바르지 않습니다.  
  
 이 옵션을 사용 하지 않는 경우 링커는 다음 메시지는 기본 스텁 프로그램 연결:  
  
```  
This program cannot be run in MS-DOS mode.  
```  
  
 가상 장치 드라이버를 빌드할 때 *filename* 는 IMAGE_DOS_HEADER 구조 (WINNT에 정의 포함 된 파일 이름을 지정할 수 있습니다 합니다. H)에서 기본 헤더가 아닌 VXD를 사용할 수 있습니다.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [Visual c + + 프로젝트 속성 설정](../../ide/working-with-project-properties.md)합니다.  
  
2.  클릭는 **링커** 폴더입니다.  
  
3.  **명령줄** 속성 페이지를 클릭합니다.  
  
4.  에 옵션을 입력에서 **추가 옵션** 상자입니다.  
  
### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)