---
title: 심각한 오류 C1210 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1210
dev_langs:
- C++
helpviewer_keywords:
- C1210
ms.assetid: e2208309-c284-425c-a7e8-48e96e66f35b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4d22a34f44fb2c97fe341cb313d7917a35506cdd
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34704986"
---
# <a name="fatal-error-c1210"></a>심각한 오류 C1210

> 설치된 런타임 버전에서는 /clr:pure 및 /clr:safe가 지원되지 않습니다.

**/clr: pure** 및 **/clr: safe** 컴파일러 옵션은 Visual Studio 2015에서는 사용 되지 않으며 Visual Studio 2017에서 지원 되지 않습니다.

현재 릴리스에 대한 컴파일러가 있지만 이전 릴리스의 공용 언어 런타임을 사용하는 경우 C1210이 발생합니다.

컴파일러의 일부 기능은 이전 버전의 런타임에서 작동하지 않을 수 있습니다.

C1210을 해결하려면 컴파일러와 함께 사용하도록 디자인된 공용 언어 런타임 버전을 설치합니다.