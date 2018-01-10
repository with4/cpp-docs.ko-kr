---
title: "-FS (동기 PDB 쓰기 적용) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /FS
dev_langs: C++
helpviewer_keywords:
- -FS compiler option [C++]
- /FS compiler option [C++]
ms.assetid: b2caaffe-f6e1-4963-b068-648f06b105e0
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cec8aa3d1b3417b6bfcb35757ac4a4a51961e16b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="fs-force-synchronous-pdb-writes"></a>/F(동기 PDB 쓰기 적용)
프로그램 데이터베이스 (PDB) 파일에 강제로 씁니다-에서 만든 [/Zi](../../build/reference/z7-zi-zi-debug-information-format.md) 또는 [/ZI](../../build/reference/z7-zi-zi-debug-information-format.md)-를 MSPDBSRV를 통해 serialize 할 수 있습니다. EXE 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/FS  
```  
  
## <a name="remarks"></a>설명  
 기본적으로 때 **/Zi** 또는 **/ZI** 지정, 컴파일러는 형식 정보와 기호 디버깅 정보를 쓰도록 PDB 파일을 잠급니다. 이렇게 하면 형식 수가 많을 경우 컴파일러가 형식 정보를 생성하는 데 걸리는 시간을 크게 줄일 수 있습니다. 다른 프로세서(예: 바이러스 백신 프로그램)가 PDB 파일을 일시적으로 잠그는 경우, 컴파일러에 의한 쓰기가 실패하고 치명적인 오류가 발생할 수 있습니다. 이 문제는 또한 여러 cl.exe 복사본이 동일한 PDB 파일에 액세스하는 경우에도 발생할 수 있습니다. 이에 대한 예로는 솔루션에 동일한 중간 디렉터리 또는 출력 디렉터리를 사용하는 독립 프로젝트가 포함되었고 병렬 빌드가 사용하도록 설정된 경우를 예로 들 수 있습니다. **/FS** 컴파일러 옵션 컴파일러에서 PDB 파일을 잠그지을 MSPDBSRV 통해 쓰기를 강제로 수행 합니다. EXE 액세스를 serialize 합니다. 이렇게 하면 빌드가 더 길어질 수 있으며, 여러 cl.exe 인스턴스가 동시에 PDB 파일에 액세스할 때 발생할 수 있는 모든 오류를 방지합니다. 독립 프로젝트가 개별 중간 및 출력 위치에 쓰기를 수행하거나 serialize된 프로젝트 빌드를 강제로 적용하기 위해 프로젝트 중 하나가 서로 종속되도록 솔루션을 변경하는 것이 좋습니다.  
  
 [/MP](../../build/reference/mp-build-with-multiple-processes.md) 옵션을 사용 하면 **/FS** 기본적으로 합니다.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  선택 된 **C/c + +** 폴더입니다.  
  
3.  선택 된 **명령줄** 속성 페이지.  
  
4.  수정 된 **추가 옵션** 포함할 속성을 `/FS` 선택한 후 **확인**합니다.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)