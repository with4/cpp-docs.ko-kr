---
title: "인수 없이 고유 조작자 작성 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: manipulators
ms.assetid: 2dc62d09-45b7-454d-bd9d-55f3c72c206d
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 9ccdd1222335cba8ba3169903f8a05e064801ccd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="writing-your-own-manipulators-without-arguments"></a>인수 없이 고유 조작자 작성
인수를 사용하지 않는 조작자를 작성할 때는 클래스 파생이 필요하지 않으며 복잡한 매크로를 사용할 필요도 없습니다. 프린터에서 \<ESC>[ 쌍을 굵은 글꼴 모드로 입력해야 한다고 가정해 보겠습니다. 이 경우 스트림에 이 쌍을 직접 삽입할 수 있습니다.  
  
```  
cout <<"regular " <<'\033' <<'[' <<"boldface" <<endl;  
```  
  
 또는 문자를 삽입하는 `bold` 조작자를 정의할 수 있습니다.  
  
```  
ostream& bold(ostream& os) {  
    return os <<'\033' <<'[';  
}  
cout <<"regular " <<bold <<"boldface" <<endl;  
```  
  
 전역적으로 정의된 `bold` 함수는 `ostream` 참조 인수를 사용하며 `ostream` 참조를 반환합니다. 이 함수는 private 클래스 요소에 액세스할 필요가 없으므로 구성원 함수나 friend가 아닙니다. `bold` 함수는 스트림에 연결됩니다. 해당 함수 유형을 허용하기 위해 스트림의 `<<` 연산자가 다음과 같은 선언을 사용하여 오버로드되기 때문입니다.  
  
```  
_Myt& operator<<(ios_base& (__cdecl *_Pfn)(ios_base&))  
{     // call ios_base manipulator  
 (*_Pfn)(*(ios_base *)this);

    return (*this);

}  
```  
  
 이 기능을 사용하여 오버로드된 다른 연산자를 확장할 수 있습니다. 이 경우 해당 기능을 사용하는 경우의 결과는 `bold`에서 스트림에 문자를 삽입하는 것과 동일합니다. 함수는 인접 문자가 인쇄될 때가 아니라 스트림에 삽입될 때 호출됩니다. 따라서 스트림의 버퍼링으로 인해 인쇄가 지연될 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [출력 스트림](../standard-library/output-streams.md)

