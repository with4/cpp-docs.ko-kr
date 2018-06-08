---
title: XDCMake 참조 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- xdcmake
dev_langs:
- C++
helpviewer_keywords:
- xdcmake program
ms.assetid: 14e65747-d000-4343-854b-8393bf01cbac
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 383347dc5cd1ce0dcadff6bdee802b90fd52e85d
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "33333907"
---
# <a name="xdcmake-reference"></a>XDCMake 참조
xdcmake.exe는 .xdc 파일을 .xml 파일로 컴파일하는 프로그램입니다. [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md)을 사용하여 소스 코드를 컴파일하는 경우 및 소스 코드 파일에 XML 태그로 표시된 문서 주석이 포함되는 경우 각 소스 코드 파일에 대해 Visual C++ 컴파일러에서 .xdc 파일이 만들어집니다.  
  
### <a name="to-use-xdcmakeexe-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 xdcmake.exe를 사용하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [프로젝트 속성 작업](../ide/working-with-project-properties.md)을 참조하세요.  
  
2.  **구성 속성** 폴더를 엽니다.  
  
3.  **XML 문서 주석** 속성 페이지를 클릭합니다.  
  
> [!NOTE]
>  명령줄의 xdcmake.exe 옵션은 xdcmake.exe가 개발 환경(속성 페이지)에서 사용되는 경우의 옵션과 다릅니다. 개발 환경에서 xdcmake.exe를 사용하는 방법은 [XML 문서 생성기 도구 속성 페이지](../ide/xml-document-generator-tool-property-pages.md)를 참조하세요.  
  
## <a name="syntax"></a>구문  
 xdcmake `input_filename options`  
  
## <a name="parameters"></a>매개 변수  
 다음은 각 문자에 대한 설명입니다.  
  
 `input_filename`  
 xdcmake.exe에 대한 입력으로 사용되는 .xdc 파일의 파일 이름입니다. 하나 이상의 .xdc 파일을 지정하거나 *.xdc를 사용하여 현재 디렉터리에서 모든 .xdc 파일을 사용합니다.  
  
 `options`  
 다음 중 0개 이상:  
  
|옵션|설명|  
|------------|-----------------|  
|/?, /help|xdcmake.exe에 대한 도움말을 표시합니다.|  
|/assembly:*filename*|.xml 파일에서 \<어셈블리> 태그의 값을 지정할 수 있습니다.  기본적으로 \<어셈블리> 태그의 값은 .xml 파일의 파일 이름과 동일합니다.|  
|/nologo|저작권 메시지를 표시하지 않습니다.|  
|/out:*filename*|.xml 파일의 이름을 지정할 수 있습니다.  기본적으로 .xml 파일의 이름은 xdcmake.exe에서 처리하는 첫 번째 .xdc 파일의 파일 이름입니다.|  
  
## <a name="remarks"></a>설명  
 Visual Studio는 프로젝트를 빌드할 때 xdcmake.exe를 자동으로 호출합니다. 명령줄에서 xdcmake.exe를 호출할 수도 있습니다.  
  
 문서 주석을 소스 코드 파일에 추가하는 방법에 대한 자세한 내용은 [문서 주석에 권장되는 태그](../ide/recommended-tags-for-documentation-comments-visual-cpp.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [XML 문서](../ide/xml-documentation-visual-cpp.md)