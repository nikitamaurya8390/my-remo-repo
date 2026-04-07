pipeline{
agent any
stages{
stage('#1.Chekout'){
steps{
git url: 'https://github.com/nikitamaurya8390/my-remo-repo',branch:'main' 
}
}


stage('#2. Build the image'){
steps{
bat 'docker build -t mywebsite .'
}
}

stage('#. stop all old containers'){
steps{
bat 'docker stop mycont || exit 0'
bat 'docker rm mycont || exit 0'
}
}

stage('$. Run the Image - Containerize'){
steps{
bat 'docker run -d -p 4000:80 --name mycont mywebsite'
}
}


}
}
