---
title: . 링커 입력으로 사용 하는 Obj 파일 | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- linker [C++], OBJ files as input
- object files, linker output
- OMF object files
- LINK tool [C++], .obj files
- COFF files
- OBJ files as linker input
- .obj files as linker input
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 57907beaa30418ce31e6c46202149048d5c9dea1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32372978"
---
# <a name="obj-files-as-linker-input"></a>링커 입력 파일로 사용하는 .Obj 파일

링커 도구 (링크입니다. EXE).obj 파일에 일반 COFF 개체 파일 형식 ()을 허용 합니다.

## <a name="remarks"></a>설명

Microsoft 공용 개체 파일 형식에 대 한 전체 설명을 제공합니다. 자세한 내용은 참조 [PE 형식](https://msdn.microsoft.com/library/windows/desktop/ms680547)합니다.

## <a name="unicode-support"></a>유니코드 지원

Visual Studio 2005 이상에서는 Microsoft Visual c + + 컴파일러는 ISO/IEC C 및 c + + 표준에 정의 된 대로 식별자에 유니코드 문자를 지원 합니다. 이전 버전의 컴파일러는 식별자에 ASCII 문자만 지원. 함수, 클래스 및 정적 변수 이름에 유니코드를 지원 하기 위해 컴파일러 및 링커에서의 유니코드 utf-8 인코딩을 사용 COFF 기호.obj 파일에 대 한 합니다. Utf-8 인코딩을 위쪽 이전 버전의 Visual Studio에서 사용 하는 ASCII 인코딩을 호환 됩니다.

컴파일러 및 링커에서의 하는 방법에 대 한 자세한 내용은 참조 [컴파일러 및 링커에서의 유니코드 지원](../../build/reference/unicode-support-in-the-compiler-and-linker.md)합니다. 유니코드 표준에 대 한 자세한 내용은 참조는 [유니코드](http://go.microsoft.com/fwlink/p/?linkid=37123) 조직입니다.

## <a name="see-also"></a>참고자료

[LINK 입력 파일](../../build/reference/link-input-files.md)  
[링커 옵션](../../build/reference/linker-options.md)  
[유니코드 지원](../../text/support-for-unicode.md)  
[컴파일러 및 링커에서의 유니코드 지원](../../build/reference/unicode-support-in-the-compiler-and-linker.md)  
[유니코드 표준](http://go.microsoft.com/fwlink/p/?linkid=37123)  
[PE 형식](https://msdn.microsoft.com/library/windows/desktop/ms680547)  
