---
title: 가져오기 라이브러리 및 내보내기 파일 빌드 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLibrarianTool.ModuleDefinitionFile
- VC.Project.VCLibrarianTool.ExportNamedFunctions
- VC.Project.VCLibrarianTool.GenerateDebug
- VC.Project.VCLibrarianTool.ForceSymbolReferences
dev_langs:
- C++
helpviewer_keywords:
- OUT library manager option
- INCLUDE library manager option
- /DEF library manager option
- exporting data
- import libraries, building
- -INCLUDE library manager option
- /OUT library manager option
- DEF library manager option
- -DEF library manager option
- -OUT library manager option
- /INCLUDE library manager option
- -EXPORT library manager option
- exporting data, export (.exp) files
- /EXPORT library manager option
- EXPORT library manager option
- .lib files
- EXP files
ms.assetid: 2fe4f30a-1dd6-4b05-84b5-0752e1dee354
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 93f817aadf2de826c628a14255ae9257be2f29ba
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32372102"
---
# <a name="building-an-import-library-and-export-file"></a>가져오기 라이브러리 및 내보내기 파일 빌드
가져오기 라이브러리를 빌드하고 파일을 내보낼 하려면 다음 구문을 사용 합니다.  
  
```  
LIB /DEF[:deffile] [options] [objfiles] [libraries]  
```  
  
 /DEF를 지정 하면 LIB에서 내보내기 사양은 LIB 명령에 전달 되는 출력 파일을 만듭니다. 권장된 사용 순서 대로 나열 된 export를 지정 하기 위한 세 가지가 있습니다.  
  
1.  A **__declspec (dllexport)** 중 하나에 정의 된 *objfiles* 또는 *라이브러리*  
  
2.  /EXPORT 사양:*이름* LIB 명령줄에서  
  
3.  에 있는 정의 **내보내기** 의 문에서 `deffile`  
  
 이들은 내보내기를 내보내는 프로그램을 링크할 때 지정 하는 데 사용 하는 동일한 방법입니다. 프로그램 둘 이상의 메서드를 사용할 수 있습니다. LIB 명령의 부분을 지정할 수 있습니다 (여러 같은 *objfiles* 또는 /EXPORT 사양) LIB 명령에 명령 파일에서와 마찬가지로에서 할 수 있는 링크 명령입니다.  
  
 다음 옵션은 가져오기 라이브러리를 빌드하는 데 적용 되며 파일 내보내기:  
  
 / 입 출력: *가져오기*  
 에 대 한 기본 출력 파일 이름을 재정의 *가져올* 만들려는 라이브러리입니다. /OUT 지정 하지 않으면 기본 이름인는 첫 번째 개체에 파일 또는 라이브러리 LIB 명령 및 확장의 기본 이름입니다. lib 합니다. 내보내기 파일 가져오기 라이브러리 및 확장명과 같은 기본 이름을 제공 됩니다. exp 합니다.  
  
 / 내보내기: *entryname*[= *internalname*] [, @ `ordinal`[, **NONAME**]] [, **데이터**]  
 다른 프로그램에서 함수를 호출 하려면 프로그램에서 함수를 내보냅니다. 데이터를 내보낼 수도 있습니다 (사용 하는 **데이터** 키워드)입니다. 내보내기는 일반적으로 DLL에 정의 됩니다.  
  
 *entryname* 호출 프로그램에서 사용 하는 것 만큼은 함수 또는 데이터 항목의 이름입니다. 지정할 수 있습니다는 *internalname* 정의 프로그램에서는 기본적으로 알려진 함수로 *internalname* 동일 *entryname*합니다. `ordinal` 지정 하지 않을 경우 범위는 1-65535; 내보내기 테이블에 있는 인덱스를 지정 `ordinal`, LIB 하나를 할당 합니다. **NONAME** 키워드는 서 수로만 하지 않고 함수를 내보내는 *entryname*합니다. **데이터** 키워드 데이터 전용 개체를 내보내는 데 사용 됩니다.  
  
 / 다음과 같습니다. `symbol`  
 기호 테이블에 지정 된 기호를 추가합니다. 이 옵션은 사용 되지 않는 포함 된 라이브러리 개체의을 강제로 적용 하는 데 유용 합니다.  
  
 Note.dll을 만들기 전에 예비 단계에서 가져오기 라이브러리를 만드는 경우 전달 해야 합니다 개체 파일의 동일한 집합.dll을 빌드할 때 가져오기 라이브러리를 빌드할 때 성공 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [가져오기 라이브러리 및 내보내기 파일을 사용한 작업](../../build/reference/working-with-import-libraries-and-export-files.md)