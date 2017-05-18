---
title: "출력 스트림 개체 생성 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- output stream objects
ms.assetid: 93c8eab6-610c-4f48-b76d-1d960cac7641
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: ca8d4e9a44f4550d02e6d224ce0130d15e81da14
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="constructing-output-stream-objects"></a>출력 스트림 개체 생성
미리 정의된 `cout`, `cerr` 또는 `clog` 개체를 사용하는 경우에만 출력 스트림을 생성할 필요가 없습니다. 다음에 대한 생성자를 사용해야 합니다.  
  
- [출력 파일 스트림 생성자](#vclrfoutputfilestreamconstructorsanchor1)  
  
- [출력 문자열 스트림 생성자](#vclrfoutputstringstreamconstructorsanchor2)  
  
##  <a name="vclrfoutputfilestreamconstructorsanchor1"></a>출력 파일 스트림 생성자  
 두 가지 방법 중 하나로 출력 파일 스트림을 생성할 수 있습니다.  
  
-   기본 생성자를 사용한 다음 `open` 멤버 함수를 호출합니다.  
  
 ```  
    ofstream myFile; // Static or on the stack  
    myFile.open("filename");

 
    ofstream* pmyFile = new ofstream; // On the heap  
    pmyFile->open("filename");
```  
  
-   생성자 호출에서 파일 이름 및 모드 플래그를 지정합니다.  
  
 ```  
    ofstream myFile("filename", ios_base::out);
```  
  
##  <a name="vclrfoutputstringstreamconstructorsanchor2"></a>출력 문자열 스트림 생성자  
 출력 문자열 스트림을 생성하려면 다음과 같은 방식으로 `ostringstream`을 사용할 수 있습니다.  
  
```  
    using namespace std;  
string sp;  
ostringstream myString;  
myString <<"this is a test" <<ends;  
sp = myString.str();
// Obtain string  
cout <<sp <endl;   
```  
  
 `ends` "조작자"는 문자열에 필요한 null 종결 문자를 추가합니다.  
  
## <a name="see-also"></a>참고 항목  
 [출력 스트림](../standard-library/output-streams.md)


