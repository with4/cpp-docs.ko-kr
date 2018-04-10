---
title: -GR (런타임 형식 정보 사용) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- /gr
- VC.Project.VCCLWCECompilerTool.RuntimeTypeInfo
- VC.Project.VCCLCompilerTool.RuntimeTypeInfo
dev_langs:
- C++
helpviewer_keywords:
- -Gr compiler option [C++]
- Gr compiler option [C++]
- RTTI compiler option
- /Gr compiler option [C++]
- enable run-time type information compiler option [C++]
ms.assetid: d1f9f850-dcec-49fd-96ef-e72d01148906
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 993465bd1666e624777e52cb1c3d3a54545589dd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="gr-enable-run-time-type-information"></a>/GR(런타임 형식 정보 사용)
런타임 시 개체 형식을 검사 하는 코드를 추가 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/GR[-]  
```  
  
## <a name="remarks"></a>설명  
 때 **/GR** 켜져, 컴파일러는 정의 `_CPPRTTI` 전처리기 매크로입니다. 기본적으로 **/GR** 켜져 있습니다. **/GR-** 런타임 형식 정보를 사용 하지 않도록 설정 합니다.  
  
 사용 하 여 **/GR** 경우 컴파일러에서 사용자 코드에서 개체 유형을 정적으로 확인할 수 없습니다. 일반적으로 필요는 **/GR** 코드를 사용 하는 경우 옵션 [dynamic_cast Operator](../../cpp/dynamic-cast-operator.md) 또는 [typeid](../../cpp/typeid-operator.md)합니다. 그러나 **/GR** 이미지의.rdata 섹션의 크기를 늘립니다. 코드를 사용 하지 않는 경우 **dynamic_cast** 또는 **typeid**, **/GR-** 더 작은 이미지를 생성할 수 있습니다.  
  
 런타임 형식 검사 하는 방법에 대 한 자세한 내용은 참조 [런타임 형식 정보](../../cpp/run-time-type-information.md) 에 *c + + 언어 참조*합니다.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  **C/C++** 폴더를 클릭합니다.  
  
3.  클릭는 **언어** 속성 페이지.  
  
4.  수정 된 **런타임 형식 정보 사용** 속성입니다.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.RuntimeTypeInfo%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)