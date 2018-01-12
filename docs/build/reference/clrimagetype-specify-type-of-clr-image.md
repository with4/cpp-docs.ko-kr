---
title: "-CLRIMAGETYPE (CLR 이미지의 형식 지정) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /CLRIMAGETYPE
- VC.Project.VCLinkerTool.CLRImageType
dev_langs: C++
helpviewer_keywords:
- /CLRIMAGETYPE linker option
- -CLRIMAGETYPE linker option
ms.assetid: 04c60ee6-9dd7-4391-bc03-6926ad0fa116
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b7d8edd6c9e62456e54ac6228f25d7f923a6813c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="clrimagetype-specify-type-of-clr-image"></a>/CLRIMAGETYPE(CLR 이미지 형식 지정)
```  
/CLRIMAGETYPE:{IJW|PURE|SAFE|SAFE32BITPREFERRED}  
```  
  
## <a name="remarks"></a>설명  
 링커에서 네이티브 개체 및 MSIL 개체를 사용 하 여 컴파일되 [/clr](../../build/reference/clr-common-language-runtime-compilation.md), /clr: pure, 또는 /clr: safe 합니다. **/clr:pure** 및 **/clr:safe** 컴파일러 옵션은 Visual Studio 2015에서는 더 이상 사용되지 않습니다. 동일한 빌드에서 혼합된 개체가 전달될 경우, 기본적으로 결과 출력 파일의 검증 가능성은 입력 모듈의 가장 낮은 검증 가능성 수준과 동일합니다. 예를 들어 안전 모듈과 순수 모듈을 모두 링커에 전달하면 출력 파일은 순수 모듈입니다. 네이티브 이미지 및 혼합된 모드 이미지를 전달 하는 경우 (사용 하 여 컴파일된 **/clr**), 결과 이미지는 혼합된 모드 이미지 됩니다.  
  
 필요한 경우, /CLRIMAGETYPE을 사용해서 낮은 수준의 검증 가능성을 지정할 수 있습니다.  
  
 .NET 4.5에서 /CLRIMAGETYPE은 SAFE32BITPREFERRED 옵션을 지원합니다. 이미지의 PE 헤더에서 이 집합은 MSIL 개체가 안전하고 모든 플랫폼에서 실행될 수 있음을 나타내지만 32비트 실행 환경이 선호됨을 나타냅니다. 이 옵션을 사용하면 응용 프로그램이 ARM 플랫폼에서 실행될 수 있으며, 64비트 실행 환경을 사용하는 대신 64비트 운영 체제의 WOW64로 실행되도록 지정합니다.  
  
 때 사용 하 여 컴파일된.exe **/clr** 또는 **/clr: pure** 실행 64 비트 운영 체제에서 응용 프로그램 실행에 32 비트 응용 프로그램 64 비트 운영 체제에서 실행할 수 있도록 wow64 합니다. 기본적으로 사용 하 여 컴파일된.exe **/clr: safe** 운영 체제의 64 비트 지원에서 실행 됩니다. 그러나 안전 응용 프로그램이 32 비트 구성 요소를 로드할 수는. 이 경우 운영 체제의 64 비트 지원에서 실행 되는 안전 이미지가 32 비트 응용 프로그램을 로드할 때 실패 합니다. 64비트 운영 체제에서 32비트 구성 요소를 로드할 때 안전 이미지가 계속 실행되도록 하려면 /CLRIMAGETYPE:SAFE32BITPREFERRED 옵션을 사용합니다. 코드를 ARM 플랫폼에서 실행할 필요가 없으면, /CLRIMAGETYPE:PURE 옵션을 지정해서 메타데이터(.corflags)를 변경하여, WOW64에서 실행되도록(및 고유 항목 기호 대체) 할 수 있습니다.  
  
 **cl /clr:safe t.cpp /link /clrimagetype:pure /entry:?main@@$$HYMHXZ /subsystem:console**  
  
 파일의 CLR 이미지 형식을 결정하는 방법에 대한 자세한 내용은 [/CLRHEADER](../../build/reference/clrheader.md)를 참조하세요.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  확장 된 **구성 속성** 노드.  
  
3.  확장 된 **링커** 노드.  
  
4.  선택 된 **고급** 속성 페이지.  
  
5.  수정 된 **CLR 이미지 형식을** 속성입니다.  
  
### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
1.  <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.CLRImageType%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)