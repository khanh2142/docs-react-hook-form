<script setup>
import { ref } from "vue";

const count = ref(0);
</script>

<template>
  <div
    class="shadow-lg p-[10px] bg-white flex flex-col gap-[10px] min-h-[100vh]"
  >
    <div class="text-[30px] text-center">Hướng dẫn sử dụng React-hook-form</div>

    <div class="flex justify-center gap-[10px]">
      <div class="flex items-center gap-[10px]">
        <img
          src="https://react-hook-form.com/images/logo/react-hook-form-logo-only.svg"
          alt=""
          class="w-[50px] hover:scale-105"
        />
        <div class="text-[20px]">React-hook-form</div>
      </div>
    </div>

    <a
      href="https://react-hook-form.com"
      class="self-center text-pink-500"
      target="_blank"
      >https://react-hook-form.com</a
    >

    <div class="text-[25px]">1.Giới thiệu về React-hook-form</div>
    <div class="text-[20px]">
      - Là 1 thư viện giúp xử lý, thao tác với form một cách dễ dàng hơn.
    </div>
    <div class="text-[20px]">- Có thể mix chung với các thư viện khác.</div>
    <div class="text-[20px]">- Control tốt, xử lý được các form phức tạp.</div>
    <div class="text-[20px]">- Tính customize cao.</div>
    <div class="text-[25px]">2.Cài đặt</div>
    <div class="text-[20px]">Câu lệnh cài đặt:</div>
    <div class="bg-slate-200 p-[5px] rounded-md">
      npm install react-hook-form
    </div>
    <div class="text-[25px]">3.Cách sử dụng</div>
    <div class="flex gap-[10px]">
      <img src="/public/docs1.png" alt="" class="w-[400px] h-[400px]" />
      <div class="flex flex-col gap-[5px]">
        <div>Chúng ta sẽ khai báo useForm() để sử dụng.</div>
        <div>
          Trong useForm sẽ có nhiều options cho chúng ta truyền vào để handle
          theo yêu cầu, phần lớn chúng ta sẽ sử dụng đến defaultValues để khai
          báo các giá trị mặc định.
        </div>
        <div>
          Các method được destruct ra từ useForm() sẽ có các công dụng như sau:
        </div>
        <div>
          + <strong>register</strong>: define và add thêm 1 nguồn dữ liệu vào
          form (có thể là input, select, v.v hoặc có thể chỉ define để sử dụng
          vào 1 trường hợp nhất định)
        </div>
        <div>
          + <strong>unregister</strong>: ngược lại với register là thêm thông
          tin vào form, thì unregister giúp loại bỏ thành phần nhất định của
          form (vd: hủy bỏ liên kết giữa input và form hiện tại)
        </div>
        <div>
          + <strong>reset</strong>: đưa tất cả giá trị của form về trạng thái
          ban đầu
        </div>
        <div>
          + <strong>watch</strong>: lấy giá trị hiện tại của 1 biến trong form
          (giống như state, khi input trong form thay đổi, nó sẽ cũng thay đổi)
        </div>
        <div>
          + <strong>control</strong>: giúp liên kết, kiểm soát các thành phần
          trong React-hook-form
        </div>
        <div>
          + <strong>setValue</strong>: giống như setState, giúp set giá trị của
          1 biến trong form
        </div>
        <div>
          + <strong>setError</strong>: giống như setValue, nhưng nó sẽ set lại
          giá trị của 1 biến trong errors
        </div>
        <div>+ <strong>errors</strong>: là 1 object chứa các lỗi của form</div>
        <div>+ <strong>handleSubmit</strong>: hàm submit form</div>
        <div>và còn nhiều thuộc tính khác, có thể tham khảo trên thư viện</div>
      </div>
    </div>

    <div class="flex gap-[10px]">
      <img src="/public/docs2.png" alt="" class="w-[600px] h-[600px]" />
      <div class="flex flex-col gap-[5px]">
        <div>
          Đối với các input thì trong dự án em đã dựng sẵn, mọi người chỉ việc
          import và bọc vào trong Controller để sử dụng (như hình)
        </div>
        <div>Controller dùng để define các input trong form</div>
        <div>
          + <strong>name</strong>: Name của input, sẽ là tên biến để mình xử lý
        </div>
        <div>
          + <strong>control</strong>: Mình sẽ truyền control từ useForm() xuống
          để quản lý form
        </div>
        <div>
          + <strong>render</strong>: render các input và truyền field xuống,
          trong field sẽ mang các props như value, onChange để truyền ngược lại
          giá trị cho form
        </div>
        <div>+ <strong>rules</strong>: Khai báo các validate cho input</div>
        <div></div>
        <div>
          Để call được hàm submit của form, chúng ta sẽ sử dụng 1 button type
          submit rồi ẩn đi, rồi sử dụng ref của nó để call hàm click(), lúc đó
          form sẽ tiến hành validate và gọi hàm onSubmit() (nếu form clean)
        </div>

        <div></div>

        <div>
          Đối với mỗi từng loại customize input của em đã làm, các props chú
          trọng cần truyền là:
        </div>

        <div>
          + <strong>field</strong>: truyền field từ controller xuống để quản lý
          (bắt buộc)
        </div>

        <div>
          + <strong>label</strong>: label của field (có thể truyền hoặc không)
        </div>

        <div>
          + <strong>errors</strong>: lỗi của field (có thể truyền hoặc không)
        </div>

        <div>
          Ngoài ra còn có nhiều props khác, mọi người có thể tham khảo code để
          biết thêm
        </div>
      </div>
    </div>

    <div class="text-[20px]">Một số trường hợp xử lý đặc biệt:</div>

    <div>
      Nếu xử lý form lồng form, hoặc form array thì ta sẽ bọc component
      FormProvider ở ngoài thẻ form ở trên
    </div>

    <div class="italic bg-slate-200 p-[5px]">
      {{ `<FormProvider {...methods}> <form></form> </FormProvider>` }}
    </div>

    <div>Ta sẽ khai báo methods như sau:</div>

    <div class="italic bg-slate-200 p-[5px]">
      {{ `const methods = useForm();` }}
    </div>

    <div>
      Khi sử dụng FormProvider thì tất cả được bọc bởi 1 form, nếu có các form
      khác ở trong thì ta chỉ cần đặt id của form khác, và delcare 1 useForm()
      khác để handle nó
    </div>

    <div>
      Trong trường hợp sử dụng list field (vd: render 1 list input nhập Họ và
      tên). Lúc này ta sẽ sử dụng tới useFieldArray()
    </div>

    <div>
      Về phía useFieldArray() sẽ hỗ trợ xử lý form dạng list, có thể
      thêm,sửa,xóa,... dựa ngay vào method của nó. Nó sẽ được register vào trong
      form như 1 biến, giá trị là []
    </div>
    <div class="text-[25px]">4.Link tham khảo</div>

    <div>
      - Link thư viện:
      <a
        href="https://react-hook-form.com"
        class="text-pink-500"
        target="_blank"
        >https://react-hook-form.com</a
      >
    </div>

    <div>
      - Link hướng dẫn:
      <a
        href="https://viblo.asia/p/react-hook-form-xu-ly-form-de-dang-hon-bao-gio-het-RnB5pAdDKPG"
        class="text-pink-500"
        target="_blank"
        >React Hook Form - xử lý form dễ dàng hơn bao giờ hết</a
      >
    </div>

    <div>
      - Link hướng dẫn:
      <a
        href="https://viblo.asia/p/react-hook-form-co-le-ban-nen-thu-07LKXmm2ZV4"
        class="text-pink-500"
        target="_blank"
        >React Hook Form - có lẽ bạn nên thử</a
      >
    </div>

    <div>
      - Link hướng dẫn:
      <a
        href="https://techmaster.vn/posts/37367/xu-ly-validate-don-gian-voi-react-hook-form"
        class="text-pink-500"
        target="_blank"
        >Xử lý validate đơn giản với React Hook Form</a
      >
    </div>
  </div>
</template>
