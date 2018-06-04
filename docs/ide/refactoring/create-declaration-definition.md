---
title: 선언/정의 만들기 | Microsoft Docs
ms.custom: ''
ms.date: 11/16/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
ms.assetid: 6b1cdcb2-765e-4b93-8cef-92b861f64eba
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 60d583ec47a3f9c5b61599a5945e3cfa0d375b1d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33331285"
---
# <a name="create-declaration--definition"></a>선언/정의 만들기
**대상:** 함수의 선언 또는 정의를 즉시 생성할 수 있습니다.

**시기:** 선언이 필요한 함수가 있거나 그 반대의 경우.  

**이유:** 선언/정의를 수동으로 만들 수 있지만, 필요한 경우 자동으로 헤더/코드 파일이 생성됩니다.

**방법:**

1. 선언 또는 정의를 만들 함수 위에 텍스트 또는 마우스 커서를 놓습니다.

   ![강조 표시된 코드](images/createdefinition_highlight.png)

1. 다음 작업 중 하나를 수행합니다.
   * **키보드**
     * **Ctrl+.** 를 눌러 **빠른 작업 및 리팩터링** 메뉴를 트리거하고 상황에 맞는 메뉴에서 **선언/정의 만들기**를 선택합니다.
   * **마우스**
     * 마우스 오른쪽 단추를 클릭하고 **빠른 작업 및 리팩터링** 메뉴를 선택하고, 상황에 맞는 메뉴에서 **선언/정의 만들기**를 선택합니다.

1. 함수의 선언/정의는 팝업 미리 보기 창에 표시되는 원본 또는 헤더 파일에서 생성됩니다.  원본 또는 헤더 파일이 없는 경우 파일이 생성되어 프로젝트에 배치됩니다.

   ![선언/정의 만들기 결과](images/createdefinition_result.png)
