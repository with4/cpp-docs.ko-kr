---
title: Windows 런타임 지원되지 않는 CRT 함수 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- unsupported CRT functions, Windows Runtime
- Windows Runtime, unsupported CRT functions
ms.assetid: bb8386d6-0ef8-460c-88d8-addff009b6f1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8db95e066b68bed4288456eccb43f737f15842d2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="windows-runtime-unsupported-crt-functions"></a>Windows 런타임 지원되지 않는 CRT 함수

많은 CRT(C 런타임) API는 Windows 런타임에서 실행되는 UWP(유니버설 Windows 플랫폼) 앱에서 사용할 수 없습니다. 이들 앱은 /ZW 컴파일러 플래그를 사용하여 빌드합니다. 지원되지 않는 CRT 함수 목록은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

모든 CRT API는 설명서의 [사전순 함수 참조](../c-runtime-library/reference/crt-alphabetical-function-reference.md) 섹션에서 설명됩니다.

## <a name="see-also"></a>참고 항목

[범주별 유버니설 C 런타임 루틴](../c-runtime-library/run-time-routines-by-category.md)<br/>
[사전순 함수 참조](../c-runtime-library/reference/crt-alphabetical-function-reference.md)<br/>
