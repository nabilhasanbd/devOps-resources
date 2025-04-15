
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




