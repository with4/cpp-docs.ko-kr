---
title: "내보내기 (함수 내보내기) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.ExportFunctions
- /export
dev_langs:
- C++
helpviewer_keywords:
- /EXPORT linker option
- EXPORT linker option
- -EXPORT linker option
ms.assetid: 0920fb44-a472-4091-a8e6-73051f494ca0
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2183a67679fc216396d03ac31a5a11db8d011454
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="export-exports-a-function"></a>/EXPORT(함수 내보내기)
```  
/EXPORT:entryname[,@ordinal[,NONAME]][,DATA]  
```  
  
## <a name="remarks"></a>설명  
 이 옵션을 다른 프로그램에서 함수를 호출할 수 있도록 프로그램에서 함수를 내보낼 수 있습니다. 데이터를 내보낼 수 있습니다. 내보내기는 일반적으로 DLL에 정의 됩니다.  
  
 *entryname* 호출 프로그램에서 사용 하는 것 만큼은 함수 또는 데이터 항목의 이름입니다. `ordinal`1-65535의에서 내보내기 테이블에 인덱스를 지정합니다. 지정 하지 않으면 `ordinal`, 링크 값을 할당 합니다. **NONAME** 키워드는 서 수로만 하지 않고 함수를 내보내는 *entryname*합니다.  
  
 **데이터** 키워드는 내보낸된 항목 데이터 항목 임을 지정 합니다. 사용 하 여 클라이언트 프로그램에서 데이터 항목을 선언 해야 **extern __declspec (dllimport)**합니다.  
  
 권장된 사용 순서 대로 나열 된 정의 내보내기 위한 세 가지가 있습니다.  
  
1.  [__declspec (dllexport)](../../cpp/dllexport-dllimport.md) 소스 코드에서  
  
2.  [내보내기](../../build/reference/exports.md) .def 파일에서 문  
  
3.  LINK 명령의 /EXPORT 사양  
  
 세 가지 방법이 모두 동일한 프로그램에서 사용할 수 있습니다. 링크 내보내기가 포함 된 프로그램을 빌드할 때 문제가 빌드에서.exp 파일을 사용 하는 한 가져오기 라이브러리도를 만듭니다.  
  
 LINK 사용 하 여 데코 레이트 형식의 식별자입니다. 컴파일러가는.obj 파일을 만들 때 식별자를 데코 레이트 합니다. 경우 *entryname* 데코레이팅되지 않은 해당 작업에 링커로 지정 됩니다 (소스 코드에 표시)으로 양식의 링크 이름 일치 시 키 려 합니다. 고유한 일치를 찾을 수 없으면 링크는 오류 메시지를 표시 합니다. 사용 하 여는 [DUMPBIN](../../build/reference/dumpbin-reference.md) 도구를는 [데코 레이트 된 이름](../../build/reference/decorated-names.md) 형식의을 링커에 지정을 할 때 식별자입니다.  
  
> [!NOTE]
>  데코 레이트 된 형식의 선언 된 C 식별자를 지정 하지 않으면 `__cdecl` 또는 `__stdcall`합니다.  
  
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