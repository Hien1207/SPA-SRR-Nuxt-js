## Serve Side Rendering và Single Page Application 
 # SSR: Gọi nó là server-side rendering là vì phần lớn logic sẽ được xử lý ở server.
    - Một số tính chất của cơ chế server side rendering:
      + Logic từ đơn giản cho đến phức tạp đều nằm ở phía server.
      + Logic để routing – chuyển trang nằm ở server.
      + Logic để render – hiển thị trang web cũng nằm ở server nốt.
    - Ưu điểm: 
      + Hỗ trợ rất mạnh việc SEO bởi vì các Search engines của Google có thể Crawler dữ liệu tốt hơn.
      + Load trang lần đầu tiên sẽ rất nhanh.
      + Hỗ trợ tốt cho các static page.
    - Nhược điểm:
      + Trang web phải xử lý lại hoàn toàn và load lại từ đầu nếu chỉ có một thay đổi nhỏ trong nội dung gây khó chịu.
      + Nặng server vì server phải xử lý nhiều logic và dữ liệu.
      + Việc xử lý nội dung HTML khiến hao tốn tài nguyên server, gây chậm trễ khi xử lý các request khác.
      + Lượng request lên server rất nhiều, do mọi tác vụ đều phải xử lý lại trên server và render lại HTML.
      + Trải nghiệm người dùng không tốt. 
# CPA: Toàn bộ source của trang web sẽ được load ngay lần đầu tiên, khi chuyển trang trình duyệt sẽ gửi những yêu cầu get dữ liệu cần thiết, chỉ load lại những nội dung thay đổi.
    - Một số tính chất của cơ chế Single Page Application:
      + Những logic đơn giản nằm ở client side
      + Logic để routing, render dữ liệu thì 96.69% là nằm ở client side
      + Logic phức tạp hoặc cần xử lý nhiều vẫn nằm ở server side.
    - Ưu điểm: 
      + Thông tin được render một lần duy nhất trên một trang duy nhất
      + Có sự phân chia công việc rõ ràng giữa FE và BE
      + Hạn chế truy vấn đến Serve
      + Hiệu quả trải nghiệm người dùng cao hơn 
    - Nhược điểm: 
      + Trình duyệt phải bật JS
      + Khó khăn trong việc SEO      
## Nuxt.Js
    - Là một framework của Vue.Js
    - Nuxt.JS có rất nhiều tính năng hữu ích, giúp bạn nhanh chóng xây dựng các ứng dụng web, có thể kể tới như:
      + Automatic Code Splitting
      + Hỗ trợ Vue hoàn hảo
      + Static File Rendering
      + Hỗ trợ phiên bản HTTP/2
      +...
    - Cấu trúc thư mục: 
         + Không có Main.js và App.vue
         + Nếu một trang không khai báo sử dụng layout nào thì default layout sẽ được dùng
         + Assets: Chứa những tài nguyên phục vụ hiển thị trang web như ảnh, fonts chữ, hay CSS…
         + Middleware: Middleware là nới bạn dùng để tạo các function mà chạy trước khi render trang.
         + Pages: Thư mục này chứa các view của ứng dụng cũng như định nghĩa routes cho ứng dụng luôn.
         + Static :Tương tự như thư mục assets nhưng mà nó cho phép truy cập trực tiếp, được map tự động với domain từ client mà không cần phải qua router hay biến môi trường.
         + Store : Chứa các tệp của vuex, dùng quản lý state của ứng dụng. Vuex Store được cài đặt kèm với Nuxt nhưng mặc định thì lại bị disable. 
         + import thư viện trong thư mục plugin dùng bất cứ đâu trong dự án khác với trong vue import ở main.js, vue.use(thư viện)
         + Routing: Cách thức hoạt động của router trong Nuxt là nó tự động tạo cấu hình vue-router dựa trên cây các tệp .vue trong thư mục pages.
         + Route lồng nhau: NuxtJS cho phép bạn tạo các route lồng nhau bằng cách sử dụng các route con của vue-router.
