---
title: 'HLSL 속성 페이지: 출력 파일 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.FXCompilerTool.AssemblerOutput
- VC.Project.FXCompilerTool.ObjectFileOutput
- VC.Project.FXCompilerTool.HeaderFileOutput
- VC.Project.FXCompilerTool.VariableName
- VC.Project.FXCompilerTool.AssemblerOutputFile
dev_langs:
- C++
ms.assetid: c5ba1e72-30de-43eb-a15a-5b0ae58e55c2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4fd1dc3ba92201567f24aa84ff8dddcd96798b38
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="hlsl-property-pages-output-files"></a>HLSL 속성 페이지: 출력 파일
HLSL 컴파일러 (fxc.exe)의 다음 속성을 구성 하려면 사용 하 여 해당 **출력 파일** 속성입니다. 액세스 하는 방법에 대 한 내용은 **출력 파일** HLSL 폴더 속성 페이지에에서 참조 [프로젝트 속성 작업](../ide/working-with-project-properties.md)합니다.  
  
## <a name="uielement-list"></a>UI 요소 목록  
 **헤더 변수 이름**  
 인코딩된 HLSL 개체 코드에 사용 되는 배열의 이름을 지정 합니다. 배열의는 HLSL 컴파일러에 의해 출력 되는 헤더 파일에 포함 되어 있습니다. 헤더 파일의 이름은으로 지정 되는 **헤더 파일 이름을** 속성입니다.  
  
 이 속성에 해당 하는 **/Vn [name]** 명령줄 인수입니다.  
  
 **헤더 파일 이름**  
 HLSL 컴파일러에 의해 출력 되는 헤더 파일의 이름을 지정 합니다. 헤더 배열에 인코딩된 HLSL 개체 코드를 포함 합니다. 배열 이름은으로 지정 됩니다는 **헤더 변수 이름** 속성입니다.  
  
 이 속성에 해당 하는 **/Fh [name]** 명령줄 인수입니다.  
  
 **개체 파일 이름**  
 HLSL 컴파일러에 의해 출력 되는 개체 파일의 이름을 지정 합니다. 기본적으로 값은 **$(OutDir) (파일 이름) %.cso**합니다.  
  
 이 속성에 해당 하는 **/Fo [name]** 명령줄 인수입니다.  
  
 **어셈블러 출력**  
 **어셈블리 전용 목록 (/ Fc)** 방금 어셈블리 언어 문을 출력 합니다. **어셈블리 코드 및 16 진수 (/ Fx)** 어셈블리 언어 문 및 16 진수에 해당 작업 코드를 모두 출력 합니다. 기본적으로 표시 안 함은 출력입니다.  
  
 **어셈블러 출력 파일**  
 HLSL 컴파일러에 의해 출력 되는 어셈블리 목록 파일의 이름을 지정 합니다.  
  
 이 속성에 해당 하는 **/Fc [name]** 및 **/Fx [name]** 명령줄 인수입니다.  
  
## <a name="see-also"></a>참고 항목  
 [HLSL 속성 페이지](../ide/hlsl-property-pages.md)   
 [HLSL 속성 페이지: 일반](../ide/hlsl-property-pages-general.md)   
 [HLSL 속성 페이지: 고급](../ide/hlsl-property-pages-advanced.md)