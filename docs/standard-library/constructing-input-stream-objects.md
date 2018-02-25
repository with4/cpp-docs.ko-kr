---
title: "입력 스트림 개체 생성 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- input stream objects
ms.assetid: ab94866e-6ffe-4f15-b4db-0bd23e636075
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a189fa948bc8c6be7acdac0dcc50e9585e82a082
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="constructing-input-stream-objects"></a>입력 스트림 개체 생성
`cin` 개체만 사용하는 경우 입력 스트림을 생성할 필요가 없습니다. 다음을 사용하는 경우 입력 스트림을 생성해야 합니다.  
  
- [입력 파일 스트림 생성자](#vclrfinputfilestreamconstructorsanchor8)  
  
- [입력 문자열 스트림 생성자](#vclrfinputstringstreamconstructorsanchor9)  
  
##  <a name="vclrfinputfilestreamconstructorsanchor8"></a>입력 파일 스트림 생성자  
 입력 파일 스트림을 만드는 방법에는 두 가지가 있습니다.  
  
-   `void` 인수 생성자를 사용한 다음 `open` 멤버 함수를 호출합니다.  
  
 ```  
    ifstream myFile; // On the stack  
    myFile.open("filename");

 
    ifstream* pmyFile = new ifstream; // On the heap  
    pmyFile->open("filename");
```  
  
-   생성자 호출에서 파일 이름 및 모드 플래그를 지정합니다. 그렇게 하면 생성 프로세스 중 파일이 열립니다.  
  
 ```  
    ifstream myFile("filename");
```  
  
##  <a name="vclrfinputstringstreamconstructorsanchor9"></a>입력 문자열 스트림 생성자  
 입력 문자열 스트림 생성자를 사용하려면 미리 할당되고 미리 초기화된 저장소의 주소가 필요합니다.  
  
```  
string s("123.45");

double amt;  
istringstream myString(s);

//istringstream myString("123.45") also works  
myString>> amt; // amt contains 123.45  
```  
  
## <a name="see-also"></a>참고 항목  
 [입력 스트림](../standard-library/input-streams.md)

