# Các gói cần cài đặt trong dotnet version 8

### Cài đặt Tools cho dự án Dotnet

```bash
dotnet tool install --global dotnet-ef
dotnet tool install --global dotnet-aspnet-codegenerator
```

### Cài đặt các gói cần thiết cho một dự án Dotnet

```bash
dotnet add package Microsoft.VisualStudio.Web.CodeGeneration.Design
dotnet add package Microsoft.EntityFrameworkCore.Design
dotnet add package Microsoft.EntityFrameworkCore.SqlServer
dotnet add package MySql.Data.EntityFramework
dotnet add package System.Data.SqlClient
dotnet add package Microsoft.EntityFrameworkCore
dotnet add package Microsoft.EntityFrameworkCore.SqlServer
dotnet add package Microsoft.EntityFrameworkCore.Design
dotnet add package Microsoft.Extensions.DependencyInjection
dotnet add package Microsoft.Extensions.Logging.Console

dotnet add package Microsoft.AspNetCore.Identity
dotnet add package Microsoft.AspNetCore.Identity.EntityFrameworkCore
dotnet add package Microsoft.VisualStudio.Web.CodeGeneration.Design
dotnet add package Microsoft.AspNetCore.Identity.UI
dotnet add package Microsoft.AspNetCore.Authentication
dotnet add package Microsoft.AspNetCore.Http.Abstractions
dotnet add package Microsoft.AspNetCore.Authentication.Cookies
dotnet add package Microsoft.AspNetCore.Authentication.Facebook
dotnet add package Microsoft.AspNetCore.Authentication.Google
dotnet add package Microsoft.AspNetCore.Authentication.JwtBearer
dotnet add package Microsoft.AspNetCore.Authentication.MicrosoftAccount
dotnet add package Microsoft.AspNetCore.Authentication.oAuth
dotnet add package Microsoft.AspNetCore.Authentication.OpenIDConnect
dotnet add package Microsoft.AspNetCore.Authentication.Twitter

dotnet add package MailKit
dotnet add package MimeKit
```

### Cài đặt Libman

```bash
dotnet tool install -g Microsoft.Web.LibraryManager.Cli
```

#### Các thư viện client-side muốn lấy về, quản lý bằng LibMan được khai báo trong một file json có tên `libman.json`, để khởi tạo ra file này hãy thực hiện lệnh

```bash
libman init
```

#### Để đưa một thư viện vào, bạn có thể khai báo nó trong libraries một cách thủ công hoặc thực hiện lệnh. Ví dụ muốn lấy về dự án thư viện CSS Bootstrap, vào CDN cdnjs tìm thì nó có tên là `twitter-bootstrap`, vậy bạn sẽ gõ lệnh sau để thêm vào:

```bash
libman install twitter-bootstrap
```

Khi lệnh thực hiện nó sẽ hỏi thư viện lấy về lưu tại đâu, do là dự án .NET nên mặc định nó gợi ý lưu vào wwwroot/lib/twitter-bootstrap bạn có thể chấp nhận hoặc gõ một đường dẫn khác.

Kết quả nó sẽ tải thư viện về, đồng thời file libman.json được cập nhật là:

```
{
  "version": "1.0",
  "defaultProvider": "cdnjs",
  "libraries": [
    {
      "library": "twitter-bootstrap@4.5.2",
      "destination": "wwwroot/lib/twitter-bootstrap"
    }
  ]
}

```

Khi bạn có file libman.json để tải tất cả các thư viện khai báo trong nó thực hiện lệnh

```bash
libman restore
```

Để cập nhật một thư viện nào đó, ví dụ jquery thì thực hiện lệnh update

```bash
libman update jquery
```
