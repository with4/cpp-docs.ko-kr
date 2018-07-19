---
title: 링커 도구 오류 LNK1211 | Microsoft Docs
ms.date: 12/05/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1211
dev_langs:
- C++
helpviewer_keywords:
- LNK1211
ms.assetid: 607400eb-4180-4892-817f-eedfa628af61
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 57948556ae7b94b9a1788b7cb4453646b5b504f1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33300386"
---
# <a name="linker-tools-error-lnk1211"></a>링커 도구 오류 LNK1211

> 미리 컴파일된 형식 정보를 찾을 수 없습니다. '*filename*' 링크 되지 않았거나 덮어

*filename* 개체 파일을 사용 하 여 컴파일된 [/Yc](../../build/reference/yc-create-precompiled-header-file.md), LINK 명령에 지정 되지 않았거나 덮어 쓰여졌습니다.

미리 컴파일된 헤더를 사용 하는 디버그 라이브러리를 만드는 경우 및 지정 하는 경우 **/Yc** 및 [/Z7](../../build/reference/z7-zi-zi-debug-information-format.md), Visual c + + 디버그 정보를 포함 하는 미리 컴파일된 개체 파일을 생성 합니다. 만 저장 하는 경우 미리 컴파일된 개체 파일을 라이브러리에이 오류가 발생 하 고 라이브러리를 사용 하 여 실행 파일 이미지를 작성 참조 되는 개체 파일에는 미리 컴파일된 개체 파일을 정의 하는 함수에 대해 전이적 참조가 없는 있습니다.

이 상황을 해결 하는 방법은 두 가지가 있습니다.

- 지정 된 [/Yd](../../build/reference/yd-place-debug-information-in-object-file.md) 컴파일러 옵션을 미리 컴파일된 헤더의 각 개체 모듈에 디버그 정보를 추가 합니다. 이 메서드는 일반적으로 응용 프로그램을 연결 하는 데 필요한 시간을 향상 시킬 수 있는 대형 개체 모듈을 생성 하기 때문에 그다지 바람직하지 않습니다.

- 지정 [/Yl](../../build/reference/yl-inject-pch-reference-for-debug-library.md) 함수 정의 포함 하지 않는 한 미리 컴파일된 헤더 파일을 만들 때 모든 임의 문자열의 이름을 전달 합니다. 컴파일러는 미리 컴파일된 개체 파일에 기호를 생성 하 고 미리 컴파일된 개체와 연결 된 미리 컴파일된 헤더 파일을 사용 하는 각 개체 파일의 기호에 대 한 참조를 내보내는 데이 방법을 사용 합니다.

사용 하 여 모듈을 컴파일할 때 **/Yc** 및 **/Yl**, 컴파일러는 기호를 비슷합니다 만듭니다 `__@@_PchSym_@00@...@symbol_name`여기서 줄임표 (...)에 저장 하 고 컴파일러에서 생성 된 문자열을 나타냅니다는 모듈의 개체입니다. 모든 원본 파일에이 미리 컴파일된 헤더를 사용 하 여 컴파일하는 링커가 개체 모듈 및 라이브러리에서 디버깅 정보를 포함 하는 지정된 된 기호를 가리킵니다.
