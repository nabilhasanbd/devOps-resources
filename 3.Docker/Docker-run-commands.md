
docker run ubuntu cat /etc/*release*
docker run ubuntu:22.04 cat /etc/*release*
    
    docker run: Runs a new Docker container.
    ubuntu: Uses the official Ubuntu image from Docker Hub.
    cat /etc/*release*: Displays Linux distribution information (like name and version).

docker run ubuntu sleep 1500
    ফোরগ্রাউন্ড মোডে রান করে (অর্থাৎ কমান্ড লাইন ব্লক করে রাখে)
    এটি একটি Ubuntu কন্টেইনার স্টার্ট করবে এবং sleep 1500 কমান্ড এক্সিকিউট করবে (যা 1500 সেকেন্ড বা 25 মিনিটের জন্য স্লিপ করবে)
    এই কন্টেইনারটি চলাকালীন আপনার টার্মিনাল/কমান্ড প্রম্পট ব্যবহার করতে পারবেন না (যতক্ষণ না কন্টেইনারটি বন্ধ হয়)
    আপনি যদি Ctrl+C প্রেস করেন, কন্টেইনারটি বন্ধ হয়ে যাবে 
docker ps (different tab)

docker run -d ubuntu sleep 1500
    ডিট্যাচড মোডে (-d ফ্ল্যাগ) রান করে (ব্যাকগ্রাউন্ডে)
    এটি একই Ubuntu কন্টেইনার স্টার্ট করবে এবং sleep 1500 কমান্ড রান করবে
    কিন্তু এটি আপনার টার্মিনালকে ব্লক করবে না - আপনি অন্যান্য কমান্ড চালাতে পারবেন
    কন্টেইনারটি ব্যাকগ্রাউন্ডে চলতে থাকবে
    আপনি docker ps কমান্ড দিয়ে দেখতে পারবেন যে কন্টেইনারটি চলছে
docker ps
docker attach "container-id"

docker run timer

docker run -d timer
docker ps
docker attacth "timer-container-id"

------------------------------

Jenkins

docker pull jenkins/jenkins
or
docker run jenkins/jenkins

in another tab
docker ps
docker inspect "container-id"

docker run -p 8080:8080 jenkins/jenkins
or
docker run -p 8080:8080 -p 50000:50000 jenkins/jenkins

docker run -p 8080:8080 -p 50000:50000 -d -v jenkins_home:/var/jenkins_home jenkins/jenkins
    docker run	একটি নতুন Docker কন্টেইনার চালু করে।
    -p 8080:8080	হোস্টের 8080 পোর্ট কে কন্টেইনারের 8080 পোর্টের সাথে যুক্ত করে (Jenkins ওয়েব ইন্টারফেস)।
    -p 50000:50000	Jenkins এজেন্ট (বিল্ড ওয়ার্কার) কমিউনিকেশনের জন্য পোর্ট ম্যাপ করে।
    -d	কন্টেইনারটি ব্যাকগ্রাউন্ডে (ডিট্যাচড মোডে) চালায়।
    -v jenkins_home:/var/jenkins_home	jenkins_home নামে একটি ডকার ভলিউম তৈরি করে Jenkins-এর সমস্ত ডেটা (/var/jenkins_home) সংরক্ষণ করে।
    jenkins/jenkins	অফিসিয়াল Jenkins Docker ইমেজ ব্যবহার করে (ডিফল্টভাবে latest ট্যাগ)।

    এটি চালানোর পরে কী হবে?
    Jenkins সার্ভার ব্যাকগ্রাউন্ডে চলতে শুরু করবে।
    আপনি ব্রাউজারে http://localhost:8080 এ গিয়ে Jenkins অ্যাক্সেস করতে পারবেন।
    প্রথমবার প্রবেশ করতে ইনিশিয়াল অ্যাডমিন পাসওয়ার্ড প্রয়োজন হবে

docker logs "container-id"
    get the password from log and go to localhost:8080 , then paste the password to enter jenkins 



