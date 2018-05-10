---
title: 입력 스트림 조작자 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- input streams, manipulators
- input stream objects
ms.assetid: 0addcacb-7b7b-4d70-9775-a59abc400fb3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 30f642dc4942491bd73265e3d647d3281f97c1e7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="input-stream-manipulators"></a>입력 스트림 조작자

많은 조작자와 같은 [setprecision](../standard-library/iomanip-functions.md#setprecision)에 대해 정의 된는 `ios` 클래스 및 따라서 입력 스트림을에 적용 합니다. 그러나 실제로 입력 스트림 개체에 영향을 주는 조작자는 거의 없습니다. 이러한 조작자 중에서 기수 조작자인 `dec`, `oct` 및 `hex`가 가장 중요하며, 입력 스트림에서 숫자에 사용된 변환 기준을 결정합니다.

추출 시 `hex` 조작자를 사용하여 다양한 입력 형식을 처리할 수 있습니다. 예를 들어 c, C, 0xc, 0xC, 0Xc 및 0XC는 모두 10진수 12로 해석됩니다. 0-9 이외의 모든 문자, A-F, a-f, x 및 X는 숫자 변환을 종료합니다. 따라서 `"124n5"` 시퀀스는 [basic_ios::fail](../standard-library/basic-ios-class.md#fail) 비트가 설정된 숫자 124로 변환됩니다.

## <a name="see-also"></a>참고자료

[입력 스트림](../standard-library/input-streams.md)<br/>
