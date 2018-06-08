---
title: 응용 프로그램 도메인 및 Visual c + + | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- interop [C++], application domains
- application domains [C++], C++
- /clr compiler option [C++], application domains
- interoperability [C++], application domains
- mixed assemblies [C++], application domains
ms.assetid: 75a08efc-9b02-40ba-99b7-dcbd71010bbf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: b935b9a5d1561fa1c8b961ee48b92f59b98e2bd2
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34704336"
---
# <a name="application-domains-and-visual-c"></a>응용 프로그램 도메인 및 Visual c + +

있는 경우는 `__clrcall` 가상 함수는 vtable 응용 프로그램 도메인 (appdomain) 됩니다. 하나의 appdomain에 개체를 만들 경우에 해당 appdomain 내에서 가상 함수를 호출할 수 있습니다. 혼합 모드에서 (**/clr**) 형식에 있으면 프로세스당 vtable을 갖습니다 `__clrcall` 가상 함수입니다. **/clr: pure** 및 **/clr: safe** 컴파일러 옵션은 Visual Studio 2015에서는 사용 되지 않으며 Visual Studio 2017에서 지원 되지 않습니다.

자세한 내용은 다음을 참조하세요.

- [appdomain](../cpp/appdomain.md)

- [__clrcall](../cpp/clrcall.md)

- [process](../cpp/process.md)

## <a name="see-also"></a>참고자료

- [혼합형(네이티브 및 관리) 어셈블리](../dotnet/mixed-native-and-managed-assemblies.md)