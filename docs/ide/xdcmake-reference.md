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
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="xdcmake-reference"></a>XDCMake 참조
xdcmake.exe는.xdc 파일을.xml 파일로 컴파일하는 프로그램입니다. 와 소스 코드를 컴파일할 때 각 소스 코드 파일에 대 한 Visual c + + 컴파일러로.xdc 파일 만들어집니다 [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) 소스 코드 파일에서 XML 태그 여 표시 된 문서 주석을 포함 하는 경우.  
  
### <a name="to-use-xdcmakeexe-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 xdcmake.exe를 사용 하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../ide/working-with-project-properties.md)합니다.  
  
2.  열기는 **구성 속성** 폴더입니다.  
  
3.  클릭는 **XML 문서 주석** 속성 페이지.  
  
> [!NOTE]
>  명령줄에서 xdcmake.exe 옵션 xdcmake.exe 개발 환경 (속성 페이지)에서 사용 되는 경우 옵션 중에서 다릅니다. 개발 환경에서 xdcmake.exe를 사용 하는 방법은 참조 하십시오. [XML 문서 생성기 도구 속성 페이지](../ide/xml-document-generator-tool-property-pages.md)합니다.  
  
## <a name="syntax"></a>구문  
 xdcmake `input_filename options`  
  
## <a name="parameters"></a>매개 변수  
 다음은 각 문자에 대한 설명입니다.  
  
 `input_filename`  
 Xdcmake.exe 입력으로 사용 되는.xdc 파일의 파일 이름입니다. 하나 이상의.xdc 파일을 지정 하거나 현재 디렉터리에 모든.xdc 파일을 사용 하도록 *.xdc 사용.  
  
 `options`  
 0 개 이상의 다음:  
  
|옵션|설명|  
|------------|-----------------|  
|/?, /help|Xdcmake.exe에 대 한 도움말을 표시 합니다.|  
|/assembly:*파일 이름*|값을 지정할 수 있습니다는 \<어셈블리 >.xml 파일의 태그에에서 있습니다.  기본적으로 값은 \<어셈블리 > 태그는.xml 파일의 파일 이름과 동일 합니다.|  
|/nologo|저작권 메시지를 표시 합니다.|  
|/out:*파일 이름*|.Xml 파일의 이름을 지정할 수 있습니다.  기본적으로.xml 파일의 이름은 xdcmake.exe에서 처리 하는 첫 번째.xdc 파일의 파일 이름입니다.|  
  
## <a name="remarks"></a>설명  
 Visual Studio는 프로젝트를 빌드할 때 xdcmake.exe를 자동으로 호출 합니다. 명령줄에서 xdcmake.exe를 호출할 수 있습니다.  
  
 참조 [문서 주석에 대 한 권장 태그](../ide/recommended-tags-for-documentation-comments-visual-cpp.md) 문서 주석을 소스 코드 파일에 추가 하는 방법에 대 한 자세한 내용은 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [XML 문서](../ide/xml-documentation-visual-cpp.md)